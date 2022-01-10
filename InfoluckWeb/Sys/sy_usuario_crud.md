## sys.sy_usuario_crud

**Procedure responsavel pelo cadastro de usuario**


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
 - login       nome do login de acesso ao sistema  
 - senha       senha
 - usuario     nome do usuario  
 - email       email do usuario
 - celular     celular do usuario
