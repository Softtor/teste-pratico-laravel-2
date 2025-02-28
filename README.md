# Teste Técnico: Desenvolvimento de API REST em Laravel

## Objetivo
Desenvolver uma **API REST** em Laravel com operações de **CRUD** (Create, Read, Update e Delete) em uma entidade principal, utilizando **autenticação de usuários**, **validação de dados**, **tratamento de erros** e **documentação** básica.

---

## Descrição Geral
O desafio consiste em criar uma aplicação Laravel capaz de gerenciar, por exemplo, uma lista de **Tarefas** (ou outra entidade de sua preferência), onde cada **usuário** possa **criar, editar e remover** apenas as suas tarefas. Deverá existir um **sistema de autenticação** para proteger as rotas que manipulam dados, permitindo que apenas usuários autenticados realizem operações.

---

## Backlog de Tarefas

### 1. Configuração Inicial
- **Tarefa**: Criar um novo projeto Laravel (versão mais recente).
- **Critérios de Aceite**:
  - Projeto deve funcionar em ambiente local (com Docker ou outro setup).
  - Projeto versionado em repositório Git (GitHub, GitLab ou similar).

### 2. Modelagem do Banco de Dados
- **Tarefa**: Criar migrations para:
  - **users** (nome, e-mail, senha, timestamps).
  - **tarefas** (título, descrição, status, usuário relacionado, timestamps).
- **Critérios de Aceite**:
  - Migrations criadas e rodando sem erros.
  - Relacionamento estabelecido (uma Tarefa pertence a um Usuário).

### 3. Autenticação e Registro de Usuário
- **Tarefa**: Implementar autenticação (JWT, Laravel Passport ou Sanctum) e rotas de registro/login.
- **Critérios de Aceite**:
  - Rota pública de registro: `POST /api/register`.
  - Rota pública de login: `POST /api/login`.
  - Geração de token de acesso para o usuário logado.

### 4. CRUD de Tarefas
- **Tarefa**: Criar rotas **protegidas** para gerenciamento de tarefas.
  - `POST /api/tarefas` (criar)
  - `GET /api/tarefas` (listar todas)
  - `GET /api/tarefas/{id}` (detalhar uma tarefa específica)
  - `PUT /api/tarefas/{id}` (atualizar)
  - `DELETE /api/tarefas/{id}` (excluir)
- **Critérios de Aceite**:
  - Apenas usuários autenticados acessam essas rotas.
  - Cada usuário só pode **editar** ou **excluir** as próprias tarefas.
  - Respostas com status HTTP adequados (200, 400, 404, etc.).

### 5. Validações e Tratamento de Erros
- **Tarefa**: Validar dados de entrada para usuários e tarefas (campos obrigatórios, formatos, etc.).
- **Critérios de Aceite**:
  - Usar as validações do Laravel (Request ou Validator).
  - Retornar mensagens claras de erro e status HTTP apropriados (400, 401, 403, 404...).

### 6. Documentação Básica
- **Tarefa**: Documentar endpoints em Markdown, Postman Collection ou Swagger.
- **Critérios de Aceite**:
  - Listar rotas, parâmetros e exemplos de requisição/resposta.
  - Explicar como obter o token e usar nos endpoints que exigem autenticação.

### 7. Testes Automatizados (Opcional / Diferencial)
- **Tarefa**: Criar testes de unidade ou integração para algumas rotas (autenticação e CRUD de tarefas).
- **Critérios de Aceite (opcional)**:
  - Testes devem rodar sem falhas com `php artisan test` ou similar.

---

## Entrega
1. Disponibilizar o código em um repositório Git (público ou privado) e conceder acesso.
2. Incluir um arquivo **README** com instruções de setup (instalação, migração, geração de token, etc.).
3. (Opcional) Incluir um arquivo de coleção do Postman ou documentação Swagger para facilitar os testes.

---

## O que será avaliado
- **Prazo**
- **Organização do código** (Estrutura de pastas, arquivos, etc.).
- **Boas práticas de Laravel** (Controllers, Services, Repositories, etc.).
- **Autenticação** e **segurança** das rotas.
- **Validações** e tratamento de erros claros.
- **Documentação** dos endpoints.
- **Qualidade dos commits** e versionamento no Git.
