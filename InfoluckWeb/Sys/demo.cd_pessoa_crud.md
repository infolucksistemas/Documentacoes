## demo.cd_pessoa_crud (p_sessao bigint,p_dados json)

###  Função responsável pela Inserção,Alteração e Deleção do cadastro de pessoa

### Parâmetro p_sessao:
```
Sessao que o usuario está logado
```

### Parâmetro p_dados:
```
Json contendo os dados da pessoa
```

### Dados contido no json:

| Coluna      | Tipo        |  Descricao           |
| ----------- | ----------- |----------------------|
| id      | integer       | Não informado para inserção, informar para alterações
| idsessao   | bigint        | Sessao do usuario logado
| versao   | bigint        | Quando insercao = 0 
| uuid   | bigint        | Gerado automaticamente
| ativo   | bigint        | Ativo ou nao
| tipopessoa   | char(1)        |Fisica ou Juridica
| nome   | text        |Nome ou Razao Social da pessoa
| apelido   | text        | Apelido ou Nome Fantasia da pessoa
| data   | date        | Data de Nascimento ou Fundação
| foto   | text        | Url da foto
| idsexo   | integer        | Id sexo referente a tabela sys.tb_sexo

### Exemplo de uso:
```
  SELECT * FROM demo.cd_pessoa_crud(
  0, 
  '{
  "id" : 32,
  "idsessao": 0,
  "versao" : 1,
  "uuid" : "9470a53d-c9b4-457d-ae9d-2c2f2d882974",
  "ativo" : true,
  "tipopessoa" : "F",
  "nome": "Tucao Labche",
  "data" : "14/04/1965",
  "foto" : "caminho da foto",
  "idsexo" : 1
  }'
  ) 
  AS 
  (
  id integer, 
  idsessao bigint, 
  versao integer, 
  uuid uuid, 
  ativo boolean, 
  tipopessoa char(1), 
  nome text, 
  data date, 
  foto text, 
  idsexo integer, 
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
| tipopessoa   | char(1)        |Fisica ou Juridica
| nome   | text        |Nome ou Razao Social da pessoa
| apelido   | text        | Apelido ou Nome Fantasia da pessoa
| data   | date        | Data de Nascimento ou Fundação
| foto   | text        | Url da foto
| idsexo   | integer        | Id sexo referente a tabela sys.tb_sexo
| erro   | text        | Possivel erro gerado na execução da função 








