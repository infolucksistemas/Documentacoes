## sys.sy_cliente_crud

**Procedure responsavel pelo cadastro de cliente da Infoluck**


#### Parametros:

```
p_sessao bigint,
p_dados json
```

### Parametro p_dados:

 - id -          integer Gerado no insert e obrigatorio em update e delete
 - idsessao -    Obrigatorio sempre
 - versao -      Gerado no insert e obrigatorio em update e delete
 - uuid -        Gerado no insert e obrigatorio em update e delete
 - ativo -       Gerado no insert e obrigatorio em update e delete
 - cliente -     Nome do Cliente
 - sigla -       Sigla que sera usado como nome do Schema, Gerar uma sigla com letras (ver como)
 - logomarca -   Caminho da imagem do logo
 - datainicial - Nao informar no crud
 - datafinal -   Nao informar no crud
 - controle -    Gerado automaticamente no insert 
 - validacao -   Gerado automaticamente no insert

### Pegar o retorno e aplicar a nova sessao simulando um novo login


pl_cliente_crud():

usuario
cliente
criar uma sessao com os dados anterior

pessoa
empresa
endereco
contato






