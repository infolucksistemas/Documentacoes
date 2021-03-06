## cep.get_endereco(p_cep text)

###  Função responsável pela busca de informações de endereço

### Parâmetro p_cep:
```
Cep no qual se deseja realizar a pesquisa ex: '13903081'
```

### Exemplo de uso:
```
select 
        * 
  from 
  cep.get_endereco('13903081') 
  as (
     id integer,
     cep text,
     endereco text,
     idbairro integer,
     idcidade integer,
     bairro text,
     codibge text,
     uf text,
     cidade text
  )
  
```

#### Exemplo de Retorno:
| Id          | Cep       |  Idbairro |  Idcidade | Bairro         | Codibge | UF | Cidade |
| ----------- | --------- |-----------|-----------|----------------|---------|----|--------|
| 219.182     | 13903081  | 14.393    |   8.886   | Jardim Alberto | 3501905 | SP | Amparo |

### Estrutura de retorno:

| Coluna      | Tipo        |  Descrição           |
| ----------- | ----------- |----------------------|
| id      | integer       | Id do endereço da consulta
| cep   | text       | Cep informado na consulta
| endereco   | text        | Endereço referente ao cep de consulta 
| idbairro   | integer        | Id do bairro da consulta
| idcidade   | integer        | Id da cidade da consulta
| bairro  | text        |Descrição do Bairro
| codibge  | text        |Código ibge do endereço 
| uf  | text        |Estado da consulta
| cidade  | text        |Descrição da Cidade








