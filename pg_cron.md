## Instalação do pg_cron 🔨

Execute o comando

```
sudo apt-get -y install postgresql-13-cron
```
*** 
Em seguida baixe o código-fonte de git `pg_cron`

```
export PATH=/usr/local/pgsql/bin:$PATH
wget https://github.com/citusdata/pg_cron/archive/master.zip
unzip master
cd pg_cron-master/
make
make install
```
***

Agora faça alterações nos arquivos .conf conforme a seguir:

`postgresql.conf`

> shared_preload_libraries = 'pg_cron' 
> 
> cron.database_name = 'menu_infoluck'

`pg_hba.conf`

> host  postgres  postgres   trust

***

Para finalizar crie a extensão `pg_cron` e conceda permissão 

```
CREATE EXTENSION pg_cron;
```
```
GRANT USAGE ON SCHEMA cron TO postgres;
```
