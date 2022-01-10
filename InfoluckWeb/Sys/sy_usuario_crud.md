## sys.sy_usuario_crud

###  Function responsável pela Inserção,Alteração e Deleção do cadastro de cliente da Infoluck

#### Parametros:

```
p_sessao bigint,
p_dados json
```

### Parâmetro p_sessao:

```
Sessao que o usuario está logado
```

### Parametro p_dados:


```
Json contendo os dados do cliente
```

### Dados contido no json:

 - id -          Gerado no insert e obrigatório em update e delete
 - idsessao -    Obrigatório sempre
 - versao -      Gerado no insert e obrigatório em update e delete
 - uuid -        Gerado no insert e obrigatório em update e delete
 - ativo -       Gerado no insert e obrigatório em update e delete
 - login -       Nome do login de acesso ao sistema  
 - senha -       Senha
 - usuario -     Nome do usuario  
 - email -       Email do usuario
 - celular -     Celular do usuario

### Exemplo de uso:

```
  Select * from sys.sy_usuario_crud(0,'[{Json com os dados}]') ;
```

#### Retorno:

```
Retorna todos os dados da tabela
```
