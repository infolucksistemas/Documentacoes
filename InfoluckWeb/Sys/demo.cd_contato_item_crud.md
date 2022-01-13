
## demo.cd_contato_item_crud(p_sessao bigint,p_dados json)

###  Função responsável pela Inserção, Alteração e Deleção do contatos da pessoa

### Parâmetro p_sessao:
```
Sessão que o usuário está logado
```

### Parâmetro p_dados:
```
Json contendo os dados da empresa
```

### Dados contido no json:

| Coluna      | Tipo        |  Descricao           |
| ----------- | ----------- |----------------------|
| id      | integer       | Não informado para inserção, informar para alterações
| idsessao   | bigint        | Sessão do usuário logado
| versao   | bigint        | Quando inserção = 0 
| uuid   | bigint        | Gerado automaticamente
| ativo   | bigint        | Ativo ou não
| idcontato  | integer        |id do cadastro de contato da tabela demo.cd_contato
| idtipocontato  | integer        |id da categoria do contato da tabela sys.tb_tipocontato (ex: EMAIL, SITE, CELULAR)
| contato  | text        |descricao do contato , exemplo djrlumoraes@gmail.com

### Exemplo de uso:
```
  Select * from demo.cd_contato_item_crud(
  0,
  '{
  "id" : 32,
  "idsessao": 0,
  "versao" : 1,
  "uuid" : "9470a53d-c9b4-457d-ae9d-2c2f2d882974",
  "ativo" : true,
  "idcontato" : 1,
  "idtipocontato" : 1,
  "contato" : "djrlumoraes@gmail.com"
  }'
  ) as
  (
   id integer, 
   idsessao bigint, 
   versao integer, 
   uuid uuid, 
   ativo boolean,
   idcontato integer, 
   idtipocontato integer,
   contato text,
   erro text
  );
  
```

#### Retorno:
| Coluna      | Tipo        |  Descricao           |
| ----------- | ----------- |----------------------|
| id      | integer       | Não informado para inserção, informar para alterações
| idsessao   | bigint        | Sessão do usuário logado
| versao   | bigint        | Quando inserção = 0 
| uuid   | bigint        | Gerado automaticamente
| ativo   | bigint        | Ativo ou não
| idcontato  | integer        |id do cadastro de contato da tabela demo.cd_contato
| idtipocontato  | integer        |id da categoria do contato da tabela sys.tb_tipocontato (ex: EMAIL, SITE, CELULAR)
| contato  | text        |descricao do contato , exemplo djrlumoraes@gmail.com
| erro   | text        | Possível erro gerado na execução da função 






