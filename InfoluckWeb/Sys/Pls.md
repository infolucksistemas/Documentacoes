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

### Estrutura para filtros das pls de pesquisa:

fields: 
[
 {field:"id"},
 {field:"idsessao"}
]

filters:
[
  {   filter: "datacad",
      arg: "entre",
      value1: "01/01/2022"
      value2: "30/01/2022"
  },
  {
      filter: "datacad",
      arg: "entre",
      value1: "01/01/2022"
      value2: "30/01/2022"
  }
  
  {
      filter: "nome",
      arg: "like",
      value1: "%Joao"
      value2: ""
  }
  
  {
      filter: "nome",
      arg: "like",
      value1: "%Joao%"
      value2: ""
  }
]
 
orders:
[
 {order:"1 asc"},
 {order:"2 desc"}
]

pages:
{page:"2",total:"100"}
