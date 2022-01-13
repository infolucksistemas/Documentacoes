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
  Select * from demo.cd_pessoa_crud(0,'[{Json com os dados}]') ;
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







