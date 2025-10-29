🏥 Med.Voll API

A Med.Voll API é uma API RESTful para gerenciar clínicas médicas de forma moderna, segura e eficiente.


Principais funcionalidades:

Cadastro de médicos e pacientes

Agendamento e cancelamento de consultas

Regras de negócio robustas (validações de horário, disponibilidade, conflito de agenda)

Autenticação e autorização com JWT


🛠️ Tecnologias Utilizadas

Java 17+

Spring Boot 3+ (REST, JPA/Hibernate)

MySQL

Spring Data JPA & Hibernate (mapeamento objeto-relacional)

Spring Security & JWT (autenticação e autorização)

Flyway (migração e versionamento de banco)

SpringDoc OpenAPI / Swagger (documentação da API)

Maven (gerenciamento de dependências)


🚀 Funcionalidades Principais
👤 Autenticação e Segurança

Login com geração de JWT

Rotas protegidas por token

👩‍⚕️ Médicos

Cadastro completo (nome, CRM, especialidade, contato, endereço)

Listagem com paginação

Atualização de informações

Exclusão lógica (inativação)

Detalhamento completo de um médico

🧍 Pacientes

Cadastro (nome, CPF, contato, endereço)

Listagem com paginação

Atualização de informações

Exclusão lógica (inativação)

Detalhamento completo de um paciente

📅 Consultas

Agendamento com regras de validação (horário da clínica, disponibilidade do médico, paciente sem conflito)

Cancelamento com antecedência mínima e motivo obrigatório

📂 Estrutura do Projeto

api/
└── src/main/java/med/voll/api/
    ├── controller/      # REST controllers
    ├── domain/          # Regras de negócio
    │   ├── consulta/    # Entidade, DTOs, repositório, validadores
    │   ├── endereco/    # Mapeamento e DTO de endereços
    │   ├── medico/      # Entidade, DTOs, repositório
    │   ├── paciente/    # Entidade, DTOs, repositório
    │   └── usuario/     # Entidade, DTOs, repositório
    └── infra/           # Infraestrutura e configurações
        ├── exception/   # Tratamento global de exceções
        ├── security/    # Configuração JWT e Spring Security
        └── springdoc/   # Configuração Swagger/OpenAPI

└── src/main/resources/
    └── db/migration/   # Scripts Flyway


🔹 Exemplos de Endpoints
Médicos

Listar Médicos: GET /medicos
Cadastrar Médico: POST /medicos

{
  "nome": "Dra. Maria Souza",
  "crm": "123456",
  "especialidade": "CARDIOLOGIA",
  "telefone": "11999999999",
  "email": "maria.souza@clinicavoll.com",
  "endereco": {
    "logradouro": "Rua das Flores",
    "numero": "123",
    "cidade": "São Paulo",
    "cep": "01234-567"
  }
}

Pacientes

Listar Pacientes: GET /pacientes
Cadastrar Paciente: POST /pacientes

{
  "nome": "João Silva",
  "cpf": "123.456.789-00",
  "telefone": "11988888888",
  "email": "joao.silva@gmail.com",
  "endereco": {
    "logradouro": "Av. Paulista",
    "numero": "1000",
    "cidade": "São Paulo",
    "cep": "01310-100"
  }
}

🏗 Boas Práticas Aplicadas

Separação de camadas: Controller → Service → Repository
Validação de dados e tratamento de exceções globais
Transações consistentes com Spring Data JPA
Testes unitários e de integração

