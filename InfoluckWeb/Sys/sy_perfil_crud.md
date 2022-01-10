## sys.sy_perfil_crud(p_sessao bigint,p_dados json)

###  Função responsável pela Inserção,Alteração e Deleção do cadastro de perfil

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
| perfil   | bigint        | Descricao do Perfil
| usuario   | boolean        | Usado para filtrar o perfil para o usuario final 


### Exemplo de uso:
```
  Select * from sys.sy_perfil_crud(0,'[{Json com os dados}]') ;
```

#### Retorno:
```
Retorna todos os dados da tabela e um campo chamado erro.
```

