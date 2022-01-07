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
