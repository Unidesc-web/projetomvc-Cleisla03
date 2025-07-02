# Sistema de Gerenciamento de Aluguel de Carros

Este é um projeto web completo desenvolvido como avaliação acadêmica, utilizando ASP.NET Core MVC. O sistema simula uma plataforma para uma locadora de veículos, permitindo o gerenciamento de carros, clientes e aluguéis, com um sistema de autenticação robusto e regras de negócio essenciais.

## 🚀 Visão Geral do Projeto

A aplicação foi construída seguindo as melhores práticas de desenvolvimento, com uma arquitetura limpa e desacoplada, focada na manutenibilidade e escalabilidade. O front-end foi personalizado para oferecer uma experiência de usuário moderna e agradável, enquanto o back-end garante a segurança e a integridade dos dados.

## ✨ Funcionalidades Principais

O sistema conta com as seguintes funcionalidades:

* **Gerenciamento de Frota (CRUD):**
    * Cadastro, visualização, edição e exclusão de veículos.
    * Campos para marca, modelo, ano, placa, preço da diária e status de disponibilidade.

* **Gerenciamento de Clientes (CRUD):**
    * Cadastro, visualização, edição e exclusão de clientes.

* **Sistema de Aluguel:**
    * Registro de novos aluguéis associando um cliente a um carro.
    * **Cálculo Automático de Valor:** O valor total do aluguel é calculado automaticamente no back-end com base no preço da diária e no período selecionado.
    * **Validação de Disponibilidade:** O sistema impede que um mesmo carro seja alugado por mais de uma pessoa no mesmo período.
    * **Validação de Datas:** A data de devolução não pode ser anterior à data de retirada.

* **Autenticação e Autorização (ASP.NET Core Identity):**
    * Sistema completo de registro de novos usuários e login.
    * Páginas protegidas: o acesso às áreas de gerenciamento (Carros, Clientes, Aluguéis) é restrito a usuários autenticados.

* **Interface de Usuário Melhorada:**
    * Página inicial personalizada com seções de destaque e "Como Funciona".
    * Notificações visuais (Toastr) para feedback de ações como criação, edição e exclusão de registros.
    * Layout responsivo com tema escuro.

## 🛠️ Tecnologias e Arquitetura

O projeto foi desenvolvido com uma pilha de tecnologias moderna e padrões de arquitetura que visam a qualidade do código.

* **Back-end:** C# com ASP.NET Core MVC (.NET 8)
* **Banco de Dados:** SQL Server com Entity Framework Core (ORM)
* **Autenticação:** ASP.NET Core Identity
* **Front-end:** HTML, CSS, JavaScript e Bootstrap 5
* **Notificações:** Biblioteca JavaScript Toastr

### Arquitetura: Padrão Repository

Um dos pilares do projeto é a utilização do **Padrão Repository**, que cria uma camada de abstração entre a lógica de negócio (nos Controllers) e o acesso aos dados (DbContext). Isso torna o código mais limpo, testável e fácil de manter.

**Exemplo da Estrutura:**

1.  **Interface (`IRepository`):** Define um "contrato" com os métodos de acesso a dados (Ex: `GetAllAsync`, `GetByIdAsync`, `AddAsync`).
2.  **Repositório Concreto (`Repository`):** Implementa a interface, contendo a lógica do Entity Framework para interagir com o banco.
3.  **Controller:** Depende da interface (e não da classe concreta) através de injeção de dependência, solicitando os dados sem saber como eles são buscados.

```csharp
// Exemplo no CarsController.cs
public class CarsController : Controller
{
    private readonly ICar
⚙️ Como Executar o Projeto
Pré-requisitos:

.NET 8 SDK

Visual Studio 2022 ou superior

SQL Server (ou LocalDB, que vem com o Visual Studio)

Configuração:

Clone este repositório para sua máquina local.

Abra a solução (.sln) no Visual Studio.

No arquivo appsettings.json, verifique se a DefaultConnection aponta para uma instância de banco de dados válida.

No Console do Gerenciador de Pacotes, execute o comando Update-Database para criar o banco de dados e aplicar todas as migrações (incluindo as tabelas do Identity).

Execução:

Pressione F5 ou o botão "Play" para iniciar a aplicação.

O sistema abrirá no seu navegador. Crie um novo usuário na página de registro para poder acessar as funcionalidades protegidas.

Projeto desenvolvido por Cleisla Eduarda Silva Vasconcelos.
