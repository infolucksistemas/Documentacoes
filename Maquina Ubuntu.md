# 🛠 - Conexão com a Máquina 

Para realizar a conexão com a máquina é necessário primeiramente realizar a instalação do [Bitvise SSH Client](https://www.bitvise.com/ssh-client-download).

Já com o Bitvise instalado faremos o Log in na máquina:

## Configuração Bitvise 🔧

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

=============================

## Utilização do Terminal 💻

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
```
E posteriormente:

```
date -u
```
"Date" trará o timezone que foi setado e "date -u" o timezone internacional.

### Disabilitar Firewall ⚙

```
sudo ufw disable
```



