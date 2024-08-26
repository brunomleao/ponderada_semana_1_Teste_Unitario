# ponderada_semana_3_Teste_Unitario

Este repositório contém os códigos baseados no artigo **Effective Unit Testing in Golang and Gin based projects** publicado no Dev.to. O objetivo é demonstrar as práticas recomendadas para escrever testes unitários em projetos que utilizam Go, Gin, GORM, e PostgreSQL.

## Estrutura do Projeto

O projeto está organizado da seguinte forma:

```
/myproject
|-- /handlers
|   |-- handler.go
|   |-- handler_test.go
|
|-- /db
|   |-- database.go
|   |-- database_test.go
|
|-- main.go
|-- go.mod
|-- go.sum
```

- **/handlers:** Contém os manipuladores de requisições HTTP para a aplicação.
- **/db:** Gerencia as conexões e consultas ao banco de dados.
- **main.go:** Ponto de entrada principal para a aplicação.
- **go.mod e go.sum:** Gerenciam as dependências do projeto.

## Configuração do Ambiente de Testes

Para executar os testes, certifique-se de ter um banco de dados PostgreSQL configurado e as dependências necessárias instaladas. Use o comando abaixo para instalar as dependências:

```bash
go mod tidy
```

## Execução dos Testes

Os testes podem ser executados utilizando o comando:

```bash
go test ./...
```

### TestUserInsertion

- **Descrição:** Este teste verifica se um usuário pode ser inserido corretamente no banco de dados.
- **Detalhes:**
  - Um usuário fictício é criado e inserido no banco de dados utilizando GORM.
  - O teste verifica se a operação de inserção ocorreu sem erros usando o framework Testify.
  - O usuário inserido é recuperado do banco de dados, e seus dados são comparados com os dados originais para garantir a consistência.

### TestUserRetrieval

- **Descrição:** Este teste verifica se os dados de um usuário podem ser recuperados corretamente do banco de dados após a inserção.
- **Detalhes:**
  - Um usuário existente no banco de dados é consultado utilizando GORM.
  - O teste verifica se a operação de recuperação ocorreu sem erros.
  - Os dados recuperados são comparados com os dados do usuário esperado para garantir que a recuperação foi bem-sucedida.

### TestUserUpdate

- **Descrição:** Este teste verifica se os dados de um usuário podem ser atualizados corretamente no banco de dados.
- **Detalhes:**
  - Um usuário existente é atualizado no banco de dados utilizando GORM.
  - O teste verifica se a operação de atualização ocorreu sem erros.
  - Os dados atualizados são consultados no banco de dados e comparados com os dados esperados para garantir a precisão da atualização.

### TestUserDeletion

- **Descrição:** Este teste verifica se um usuário pode ser removido corretamente do banco de dados.
- **Detalhes:**
  - Um usuário existente é deletado do banco de dados utilizando GORM.
  - O teste verifica se a operação de deleção ocorreu sem erros.
  - O teste tenta recuperar o usuário deletado e verifica se o registro não é encontrado, confirmando que a deleção foi bem-sucedida.

## Considerações Finais

Este projeto foi criado para ilustrar as práticas de testes unitários descritas no artigo original. Os códigos incluídos no repositório foram copiados diretamente do artigo mencionado, sem modificações ou adições. Eles servem como exemplos práticos de testes unitários utilizando as ferramentas mencionadas (Gin, GORM, PostgreSQL, Testify). Para mais detalhes sobre a lógica e o funcionamento dos testes, consulte o [artigo no Dev.to](https://dev.to/nileshprasad137/effective-unit-testing-in-a-golang-project-with-gin-gorm-and-postgresql-1ld5).
