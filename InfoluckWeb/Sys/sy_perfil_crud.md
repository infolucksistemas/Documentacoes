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

- id        integer,
- idsessao  bigint,
- versao    integer,
- uuid      uuid,
- ativo     boolean,
- perfil    text,
- usuario   boolean

### Exemplo de uso:
```
  Select * from sys.sy_perfil_crud(0,'[{Json com os dados}]') ;
```

#### Retorno:
```
Retorna todos os dados da tabela e um campo chamado erro.
```

