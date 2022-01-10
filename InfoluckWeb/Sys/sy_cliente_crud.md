## sys.sy_cliente_crud

**Procedure responsável pelo cadastro de cliente da Infoluck**


#### Parâmetros:

```
p_sessao bigint
p_dados json
```

### Parâmetro p_dados:

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

### Pegar o retorno e aplicar a nova sessão simulando um novo login


pl_cliente_crud():

usuario
cliente
criar uma sessão com os dados anterior

pessoa
empresa
endereco
contato






