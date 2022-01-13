## sys.sy_perfil_crud(p_sessao bigint,p_dados json)

###  Função responsável pela Inserção,Alteração e Deleção do cadastro de perfil

### Parâmetro p_sessao:
```
Sessao que o usuario está logado
```

### Parâmetro p_dados:
```
Json contendo os dados do cliente
```

### Dados contido no json:

| Coluna      | Tipo        |  Descricao           |
| ----------- | ----------- |----------------------|
| id      | integer       | Não informado para inserção, informar para alterações
| idsessao   | bigint        | Sessao do usuario logado
| versao   | bigint        | Quando insercao = 0 
| uuid   | bigint        | Gerado automaticamente
| ativo   | bigint        | Ativo ou nao
| perfil   | bigint        | id do Perfil referente a tabela sys.sy_perfil
| usuario   | boolean        | Usado para filtrar o perfil para o usuario final 


### Exemplo de uso:
```
  Select * from sys.sy_perfil_crud(
  0,
  '
  '{
  "id" : 32,
  "idsessao": 0,
  "versao" : 1,
  "uuid" : "9470a53d-c9b4-457d-ae9d-2c2f2d882974",
  "ativo" : true,
  "perfil" : 1,
  "usuario": true
  }'
  ) as
  (
   id integer, 
   idsessao bigint, 
   versao integer, 
   uuid uuid, 
   ativo boolean,
   perfil bigint, 
   erro text
  );
```

#### Retorno:

| Coluna      | Tipo        |  Descricao           |
| ----------- | ----------- |----------------------|
| id      | integer       | Não informado para inserção, informar para alterações
| idsessao   | bigint        | Sessao do usuario logado
| versao   | bigint        | Quando insercao = 0 
| uuid   | bigint        | Gerado automaticamente
| ativo   | bigint        | Ativo ou nao
| perfil   | bigint        | Descricao do Perfil
| usuario   | boolean        | Usado para filtrar o perfil para o usuario final 
| erro   | text        | Possivel erro gerado na execução da função


