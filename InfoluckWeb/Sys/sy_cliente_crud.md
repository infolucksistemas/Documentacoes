## sys.sy_cliente_crud(p_sessao bigint,p_dados json)

###  Função responsável pela Inserção,Alteração e Deleção do cadastro de cliente da Infoluck

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
| cliente   | text        |Nome do Cliente
| sigla   | text        | Sigla que será usado como nome do Schema, gerar uma sigla com letras (ver como)
| logomarca   | text        | Caminho da imagem do logo
| datainicial   | text        | Não informar no crud
| datafinal   | text        | Não informar no crud
| controle   | text        | Gerado automaticamente no insert 
| validacao   | text        | Gerado automaticamente no insert 



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


## Obs

```
Para cadastrar um novo cliente:

- Cadastrar um novo usuario desse cliente.
- Cadastrar o novo cliente.
- Fazer login com esse novo usuario para pegar a sessao
- Cadastrar Pessoa
- Cadastrar Empresa
- Cadastrar Endereco
- Cadastrar Contato

```







