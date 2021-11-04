## 🛠 Conexão com a Máquina

Para realizar a conexão com a máquina é necessário primeiramente realizar a instalação do [Bitvise SSH Client](https://www.bitvise.com/ssh-client-download).

Já com o Bitvise instalado faremos o Log in na máquina:

## **🔨 - Configuração Bitvise**

### - Aba Login

#### Server
- Host = 192.168.1.104
- Port = 22

#### Authentication
- Username = infoluck
- Initial method = none
- Elevation = Default

**Ao clicar em "Log in" será requisitado o password:**

#### User Authentication
- Username = infoluck
- Method = password
- Password = root

## **💻 - Utilização do Terminal**

Para acessar o terminal é precisa clicar em **"New Terminal Console"**, nele faremos todas as configurações e instalações necessárias para a utilização da máquina.

### Ajuste do Timezone ⏰

Para ajustar o timezone digite no terminal:
```
sudo dpkg-reconfigure tzdata
```
Agora basta configurar para America->São-Paulo.

Para conferir se foi setado o fuso horário correto digite:
```
date
date -u
```
"Date" trará o timezone que foi setado e "date -u" o timezone internacional.

### Disabilitar Firewall ⚙

Para que mais para frente na instalação do postgres e afins não precisemos abrir portas no firewall o desabilitaremos 

```
sudo ufw disable
```

### Instalação Apache e PHP 🔑 

Agora podemos iniciar as instalações. Vamos iniciar instalando Apache e PHP7.
Habilitaremos módulos como opcache (aceleração), gd (imagens) e mbstring (unicode).

```
sudo apt-get update
sudo apt-get install apache2 php libapache2-mod-php
sudo apt-get install php-soap php-xml php-curl php-opcache php-gd php-mbstring
```

Em seguida, habilitaremos os módulos do apache:

```
a2dismod mpm_event
a2dismod mpm_worker
a2enmod mpm_prefork
sudo a2enmod rewrite
sudo a2enmod php7.4
```

**(Opcional)** É possível ajustar algumas configurações do PHP, como habilitar a exibição de log de erros, aumentar o limite de uso de RAM, o tempo de execução, o tempo de sessão, e definir limites de upload.

```
echo "" >> /etc/php/7.4/apache2/php.ini
echo "error_log = /tmp/php_errors.log" >> /etc/php/7.4/apache2/php.ini
echo "display_errors = On"             >> /etc/php/7.4/apache2/php.ini
echo "memory_limit = 256M"             >> /etc/php/7.4/apache2/php.ini
echo "max_execution_time = 120"        >> /etc/php/7.4/apache2/php.ini
echo "error_reporting = E_ALL"         >> /etc/php/7.4/apache2/php.ini
echo "file_uploads = On"               >> /etc/php/7.4/apache2/php.ini
echo "post_max_size = 100M"            >> /etc/php/7.4/apache2/php.ini
echo "upload_max_filesize = 100M"      >> /etc/php/7.4/apache2/php.ini
echo "session.gc_maxlifetime = 14000"  >> /etc/php/7.4/apache2/php.ini
```

**(Recomendado)** Quando a aplicação entrar em produção, desligue a exibição de erros. Você pode também ser mais tolerante quanto ao nível de erros a ser reportado.
```
echo "display_errors = Off" >> php.ini
echo "error_reporting = E_ALL & ~E_DEPRECATED & ~E_STRICT & ~E_NOTICE" >> php.ini
```

Quando tudo estiver configurado, restarte o apache:
```
service apache2 restart
```
