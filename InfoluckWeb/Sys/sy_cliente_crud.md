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

 - id -          Integer gerado no insert e obrigatório em update e delete
 - idsessao -    Obrigatório sempre
 - versao -      Gerado no insert e obrigatório em update e delete
 - uuid -        Gerado no insert e obrigatório em update e delete
 - ativo -       Gerado no insert e obrigatório em update e delete
 - cliente -     Nome do Cliente
 - sigla -       Sigla que será usado como nome do Schema, gerar uma sigla com letras (ver como)
 - logomarca -   Caminho da imagem do logo
 - datainicial - Não informar no crud
 - datafinal -   Não informar no crud
 - controle -    Gerado automaticamente no insert 
 - validacao -   Gerado automaticamente no insert

### Exemplo de uso:
```
  Select * from sys.sy_cliente_crud(0,'[{Json com os dados}]') ;
```

#### Retorno:
```
Retorna todos os dados da tabela e um campo chamado erro.
```

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







