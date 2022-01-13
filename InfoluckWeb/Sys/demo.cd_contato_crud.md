
## demo.cd_contato_crud (p_sessao bigint,p_dados json)

###  Função responsável pela Inserção, Alteração e Deleção do contatos da pessoa

### Parâmetro p_sessao:
```
Sessão que o usuário está logado
```

### Parâmetro p_dados:
```
Json contendo os dados da empresa
```

### Dados contido no json:

| Coluna      | Tipo        |  Descricao           |
| ----------- | ----------- |----------------------|
| id      | integer       | Não informado para inserção, informar para alterações
| idsessao   | bigint        | Sessão do usuário logado
| versao   | bigint        | Quando inserção = 0 
| uuid   | bigint        | Gerado automaticamente
| ativo   | bigint        | Ativo ou não
| idpessoa  | integer        |id do cadastro de pessoa
| idcategoriacontato  | integer        |id da categoria do contato da tabela sys.tb_categoriacontato (ex: RESIDENCIAL)
| contato  | text        |descricao do contato

### Exemplo de uso:
```
  Select * from demo.cd_empresa_crud(0,'[{Json com os dados}]') ;
  
  Select * from demo.cd_empresa_crud(
  0,
  '{
  "id" : 32,
  "idsessao": 0,
  "versao" : 1,
  "uuid" : "9470a53d-c9b4-457d-ae9d-2c2f2d882974",
  "ativo" : true,
  "idpessoa" : 1,
  "idcategoriacontato" : 1,
  "contato" : "Luciano"
  }'
  ) as
  (
   id integer, 
   idsessao bigint, 
   versao integer, 
   uuid uuid, 
   ativo boolean,
   idpessoa integer, 
   contato text,
   erro text
  );
  
```

#### Retorno:
| Coluna      | Tipo        |  Descricao           |
| ----------- | ----------- |----------------------|
| id      | integer       | Não informado para inserção, informar para alterações
| idsessao   | bigint        | Sessão do usuário logado
| versao   | bigint        | Quando inserção = 0 
| uuid   | bigint        | Gerado automaticamente
| ativo   | bigint        | Ativo ou não
| idpessoa  | integer        |id do cadastro de pessoa
| idcategoriacontato  | integer        |id da categoria do contato da tabela sys.tb_categoriacontato (ex: RESIDENCIAL)
| contato  | text        |descricao do contato
| erro   | text        | Possível erro gerado na execução da função 






