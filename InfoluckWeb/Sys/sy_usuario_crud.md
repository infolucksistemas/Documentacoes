## sys.sy_usuario_crud(p_sessao bigint,p_dados json)

###  Função responsável pela Inserção,Alteração e Deleção do cadastro de cliente da Infoluck

### Parâmetro p_sessao:
```
Sessao que o usuario está logado
```

### Parametro p_dados:
```
Json contendo os dados do usuário
```

### Dados contido no json:

| Coluna      | Tipo        |  Descricao           |
| ----------- | ----------- |----------------------|
| id      | integer       | Não informado para inserção, informar para alterações
| idsessao   | bigint        | Sessao do usuario logado
| versao   | bigint        | Quando insercao = 0 
| uuid   | bigint        | Gerado automaticamente
| ativo   | bigint        | Ativo ou nao
| login   | text        |Nome do login de acesso ao sistema 
| senha   | text        |Senha
| usuario   | text        | Nome do usuario 
| email   | text        | Email do usuario
| celular   | text        | Celular do usuario

### Exemplo de uso:

```
  SELECT * FROM sys.sy_usuario_crud(
  0, 
  '{"id" : 32,
  "idsessao": 0,
  "versao" : 1,
  "uuid" : "9470a53d-c9b4-457d-ae9d-2c2f2d882974",
  "ativo" : true,
  "login" : "pauloinfoluck",
  "senha": "info@luck",
  "usuario" : "Paulo Vitor",
  "email" : "paulo@infoluck.com.br",
  "celular" : "19999021510"}'
  ) 
  AS 
  (
  id integer, 
  idsessao bigint, 
  versao integer, 
  uuid uuid, 
  ativo boolean, 
  login text, 
  senha text, 
  usuario text, 
  email text, 
  celular text, 
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
| login   | text        |Nome do login de acesso ao sistema 
| senha   | text        |Senha
| usuario   | text        | Nome do usuario 
| email   | text        | Email do usuario
| celular   | text        | Celular do usuario
| erro   | text        | Possivel erro gerado na execução da função
