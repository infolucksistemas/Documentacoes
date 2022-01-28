## sys.sy_login_crud(p_sessao bigint,p_dados json)

###  Função responsável por processar a manipulação de dados na tabela sys.sy_login: -> p_sessao = Id da sessão do usuário logado; -> p_dados = Dados da tabela no formato json.

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
| versao   | integer        | Quando insercao = 0 
| uuid   | uuid        | Gerado automaticamente
| ativo   | boolean        | Ativo ou nao
| datahora     | text        |Nome do Cliente
| login   | text        | Sigla que será usado como nome do Schema, gerar uma sigla com letras (ver como)
| senha        | text        | Caminho da imagem do logo
| sucesso        | boolean        | Não informar no crud 


### Exemplo de uso:
```
  Select * from sys.sy_cliente_crud(0,'[{Json com os dados}]') ;
  
  SELECT * FROM sys.sy_cliente_crud(
  0, 
  '{"id" : 32,
  "idsessao": 0,
  "versao" : 1,
  "uuid" : "9470a53d-c9b4-457d-ae9d-2c2f2d882974",
  "ativo" : true,
  "cliente" : "Tucao Lanches",
  "sigla": "aaabbb123",
  "logomarca" : "Caminho da imagem da logo"
  }'
  ) 
  AS 
  (
  id integer, 
  idsessao bigint, 
  versao integer, 
  uuid uuid, 
  ativo boolean, 
  cliente text,
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
| cliente   | text        |Nome do Cliente
| sigla   | text        | Sigla que será usado como nome do Schema, gerar uma sigla com letras (ver como)
| logomarca   | text        | Caminho da imagem do logo
| datainicial   | text        | Não informar no crud
| datafinal   | text        | Não informar no crud
| controle   | text        | Gerado automaticamente no insert 
| validacao   | text        | Gerado automaticamente no insert 
| erro   | text        | Possivel erro gerado na execução da função 








