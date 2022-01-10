## sys.sy_cliente_crud

**Procedure responsavel pelo cadastro de cliente da Infoluck**


#### Parametros:

```
p_sessao bigint,
p_dados json
```

### Parametro p_dados:

 - id          integer Gerado no insert e obrigatorio em update e delete
 - idsessao    bigint Obrigatorio sempre
 - versao      integer Gerado no insert e obrigatorio em update e delete
 - uuid        uuid Gerado no insert e obrigatorio em update e delete
 - ativo       boolean Gerado no insert e obrigatorio em update e delete
 - cliente     text Nome do Cliente
 - sigla       text Sigla que sera usado como nome do Schema, Gerar uma sigla com letras (ver como)
 - logomarca   text Caminho da imagem do logo
 - datainicial text Nao informar no crud
 - datafinal   text Nao informar no crud
 - controle    text Gerado automaticamente no insert 
 - validacao   text  Gerado automaticamente no insert

### Pegar o retorno e aplicar a nova sessao simulando um novo login


pl_cliente_crud():

usuario
cliente
criar uma sessao com os dados anterior

pessoa
empresa
endereco
contato






