## sys.sy_usuario_crud(p_sessao bigint,p_dados json)

###  Função responsável pela Inserção,Alteração e Deleção do cadastro de cliente da Infoluck

### Parâmetro p_sessao:
```
Sessao que o usuario está logado
```

### Parametro p_dados:
```
Json contendo os dados do usuário
```

### Dados contido no json:


| Coluna      | Tipo        |  Descricao           |
| ----------- | ----------- |----------------------|
| id      | integer       | Não informado para inserção, informar para alterações
| idsessao   | bigint        | Sessao do usuario logado
| versao   | bigint        | Quando insercao = 0 
| uuid   | bigint        | Gerado automaticamente
| ativo   | bigint        | Ativo ou nao
| login   | text        |Nome do login de acesso ao sistema 
| senha   | text        |Senha
| usuario   | text        | Nome do usuario 
| email   | text        | Email do usuario
| celular   | text        | Celular do usuario

### Exemplo de uso:

```
  Select * from sys.sy_usuario_crud(0,'[{Json com os dados}]') ;
```

#### Retorno:

```
Retorna todos os dados da tabela e um campo chamado erro.
```
