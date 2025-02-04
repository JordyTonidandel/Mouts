# Ambev.DeveloperEvaluation

## Descrição

A **Ambev.DeveloperEvaluation** é um projeto de avaliação para desenvolvedor sênior .NET. O objetivo do projeto é implementar uma API de vendas com funcionalidades completas, incluindo regras de negócios específicas, integração com banco de dados, documentação, e testes.

---

## Tecnologias Utilizadas

O projeto foi desenvolvido utilizando as seguintes tecnologias:

### Backend
- **.NET 8.0**: Plataforma de desenvolvimento para criação de aplicações modernas.
- **C#**: Linguagem de programação utilizada para o desenvolvimento do backend.

### Banco de Dados
- **PostgreSQL**: Banco de dados relacional utilizado para persistência principal.
- **MongoDB**: Banco de dados não relacional utilizado para logs e armazenamento de eventos.

### Frameworks e Ferramentas
- **Entity Framework Core**: ORM para interação com o PostgreSQL.
- **MediatR**: Para implementação do padrão Mediator.
- **AutoMapper**: Para mapeamento de objetos entre DTOs e entidades.
- **Rebus**: Para simulação de mensagens de eventos.
- **Swagger**: Documentação interativa da API.
- **xUnit**: Framework de testes unitários.
- **NSubstitute**: Biblioteca de mocking para testes.
- **Bogus (Faker)**: Geração de dados fictícios para testes.

---

## Funcionalidades

A API implementa as seguintes funcionalidades:

### Endpoints de Vendas (`/sales`)
- **Criar uma venda (`POST /sales`)**
- **Obter todas as vendas (`GET /sales`)**
- **Obter uma venda por ID (`GET /sales/{id}`)**
- **Atualizar uma venda (`PUT /sales/{id}`)**
- **Cancelar uma venda (`DELETE /sales/{id}`)**

### Regras de Negócio
1. **Descontos por Quantidade**:
   - Compras de 4+ itens: 10% de desconto.
   - Compras de 10-20 itens: 20% de desconto.
   - Limite máximo: 20 itens por produto.
   - Menos de 4 itens: sem desconto.
2. **Status da Venda**:
   - Criada, Modificada, Cancelada.
3. **Eventos de Domínio**:
   - Publicação de eventos para `SaleCreated`, `SaleModified`, `SaleCancelled`, `ItemCancelled`.

---

## Estrutura do Projeto

A organização segue o padrão de camadas, facilitando a separação de responsabilidades:

root/ 
  ├── src/
    │ ├── Application/ # Casos de uso e validações 
    │ ├── Domain/ # Entidades e regras de negócio 
    │ ├── Infrastructure/ # Repositórios e integração com DB 
    │ ├── API/ # Controllers e configuração da API 
  ├── tests/ │
    ├── UnitTests/ # Testes unitários 
    │ ├── IntegrationTests/ # Testes de integração 
  └── README.md # Documentação do projeto

  
---

## Configuração e Execução

### Pré-requisitos
Certifique-se de ter instalado:
- [.NET 8.0 SDK](https://dotnet.microsoft.com/download)
- [PostgreSQL](https://www.postgresql.org/download/)
- [MongoDB](https://www.mongodb.com/try/download/community)

### Passos para Executar
1. Clone o repositório:
   ```bash
   git clone https://github.com/JordyTonidandel/Mouts.git
   cd Mouts
