## Instalação do pg_cron 🔨

Execute o comando

```
sudo apt-get -y install postgresql-13-cron
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

Agende o cron no banco de dados:

Programe o cron para executar a função a cada 2 minutos 

```
SELECT cron.schedule('*/2 * * * *', $$select insert_itn_count()$$);
```

Programe o cron para executar a tarefa todos os dias às 10h

```
SELECT cron.schedule('0 10 * * *', 'VACUUM');
```

Você pode ver os cronogramas conforme abaixo:

```
SELECT * FROM cron.job;
```

