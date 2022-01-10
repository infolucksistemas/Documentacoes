## sys.sy_usuario_crud

**Procedure responsavel pelo cadastro de usuario**


#### Parametros:

```
p_sessao bigint,
p_dados json
```

### Parametro p_dados:

 - id -          Gerado no insert e obrigatorio em update e delete
 - idsessao -    Obrigatorio sempre
 - versao -      Gerado no insert e obrigatorio em update e delete
 - uuid -        Gerado no insert e obrigatorio em update e delete
 - ativo -       Gerado no insert e obrigatorio em update e delete
 - login -       Nome do login de acesso ao sistema  
 - senha -       Senha
 - usuario -     Nome do usuario  
 - email -       Email do usuario
 - celular -     Celular do usuario


#### Retorno:

```
Retorna todos os dados da tabela
```
