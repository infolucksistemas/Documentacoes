## demo.cd_empresa_crud (p_sessao bigint,p_dados json)

###  Função responsável pela Inserção, Alteração e Deleção do cadastro de empresa.

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
```

#### Retorno:
| Coluna      | Tipo        |  Descricao           |
| ----------- | ----------- |----------------------|
| id      | integer       | Não informado para inserção, informar para alterações
| idsessao   | bigint        | Sessão do usuário logado
| versao   | bigint        | Quando inserção = 0 
| uuid   | bigint        | Gerado automaticamente
| ativo   | bigint        | Ativo ou não
| cliente   | text        |Nome do Cliente
| sigla   | text        | Sigla que será usado como nome do Schema, gerar uma sigla com letras (ver como)
| logomarca   | text        | Caminho da imagem do logo
| datainicial   | text        | Não informar no crud
| datafinal   | text        | Não informar no crud
| controle   | text        | Gerado automaticamente no insert 
| validacao   | text        | Gerado automaticamente no insert 
| erro   | text        | Possível erro gerado na execução da função 


## Obs

```
Para cadastrar um novo cliente:

- Cadastrar um novo usuário desse cliente.
- Cadastrar o novo cliente.
- Fazer login com esse novo usuário para pegar a sessao
- Cadastrar Pessoa
- Cadastrar Empresa
- Cadastrar Endereço
- Cadastrar Contato

```






