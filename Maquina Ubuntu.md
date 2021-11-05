## 📃 Indice
- [Conexão com a Maquina](#-conexão-com-a-máquina)
- [Configuração Bitvise](#---configuração-bitvise)
- [Utilização do Terminal](#---utilização-do-terminal)
- [Ajuste do Timezone](#ajuste-do-timezone-)
- [Desabilitar Firewall](#desabilitar-firewall-)
- [Instalação Apache e PHP](#instalação-apache-e-php-)
- [Configuração do Apache](#configuração-do-apache-)
- [Instalação do Postgres](#instalação-do-postgres-)
- [Configuração do Postgres](#configuração-do-postgres-)

***

## 🖥 Conexão com a Máquina

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

***

## **💻 - Utilização do Terminal**

Para acessar o terminal é precisa clicar em **"New Terminal Console"**, nele faremos todas as configurações e instalações necessárias para a utilização da máquina.
###

![Acessar terminal](acess_terminal_att.png)

### Ajuste do Timezone ⏰

Para ajustar o timezone digite no terminal:
```
sudo dpkg-reconfigure tzdata
```
Agora basta configurar para `America->São-Paulo`.

Para conferir se foi setado o fuso horário correto digite:
```
date
date -u
```
"Date" trará o timezone que foi setado e "date -u" o timezone internacional.

### Desabilitar Firewall ⚙

Para que mais para frente na instalação do postgres e afins não precisemos abrir portas no firewall o desabilitaremos 

```
sudo ufw disable
```
***

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
sudo a2dismod mpm_event
sudo a2dismod mpm_worker
sudo a2enmod mpm_prefork
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
***
### Configuração do Apache ⚙
Primeiro setaremos permissão para modificar a pasta `/var/www/`:
```
sudo chown -R $USER:$USER "/var/www/"
``` 
Para subirmos o projeto no localhost deveremos enviar a pasta do projeto em php para dentro da pasta `/var/www/html` usando o SFTP.
![Config www](sftp_html.png)

Agora configuraremos os arquivos do host, acesse a seguinte pasta: 
> /etc/apache2/sites-available/example.com.conf

As modificações serão realizadas de acordo com as necessidades atuais 
```
<VirtualHost *:80>                                  #Porta 
    ServerAdmin infoluck@infoluck.com.br            #Onde será recebido os e-mails
    DocumentRoot /var/www/html                      #Pasta onde se encontra nossa aplicação php
    ServerName exemplo.com                          #Domínio base (Opcional)
    ServerAlias www.exemplo.com                     #Define os outros nomes que devem corresponder como se fossem o nome base (Opcional)
    ErrorLog ${APACHE_LOG_DIR}/error.log            #Default
    CustomLog ${APACHE_LOG_DIR}/access.log combined #Default
</VirtualHost>
```
***
### Instalação do Postgres 🛠

Para instalarmos o Postgres13 executaremos os seguintes comandos:
```
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get -y install postgresql-13
```

### Configuração do Postgres ⚙

Agora editaremos o arquivo `pg_hba.conf` pelo NANO.

#### ALGUNS COMANDOS DO NANO:
> CTRL + W -> Pesquisar Palavras
>
> ALT + W -> Próxima Palavra
> 
> CTRL + O -> Salvar
> 
> CTRL + X -> Sair 

Digite:

```
 sudo nano /etc/postgresql/13/main/pg_hba.conf
```

### Altere a linha:
> IPv4 local connections:
> host    all             all             127.0.0.1/32            md5
### Para:
> IPv4 local connections:
> host    all             all             0.0.0.0/0            md5

Agora faremos alteração no arquivo `postgresql.conf`.

```
 sudo nano /etc/postgresql/13/main/postgresql.conf
```

### Altere as linhas:
> #listen_addresses = 'localhost'
>
> datestyle = 'iso, mdy' 	
### Respectivamente para:
> listen_addresses = '*'
> 
> datestyle = 'iso, dmy' 	

### Verifique também se a linha de timezone se encontra da seguinte forma:
> timezone = 'America/Sao_Paulo'




