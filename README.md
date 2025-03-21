# Projeto - Aplicações de aprendizagem e gestão

## Introdução

Esse projeto é uma plataforma educacional completa feita pra melhorar o aprendizado e a administração da escola. Integra duas aplicações principais:

1. **Projeto 1** - Um sistema de aprendizagem com livros online, plataformas de testes, índices de preparação e aulas de e-learning.
2. **Projeto 2** - Um sistema de gestão escolar que gere os dados dos alunos, a assiduidade, os registos financeiros e os calendários de exames.

### Objetivos

- Fornecer uma plataforma de aprendizagem e gestão tudo-em-um para alunos, professores e administradores.
- Ajudar os alunos a acompanhar o seu progresso de aprendizagem e a melhorar através de testes interactivos e e-learning.
- Permitir que as instituições de ensino façam uma gestão eficiente dos registos dos alunos, das contas financeiras e da calendarização.

---

## Compreender o Pugnatrix e o Gescola

### Pugnatrix

O Pugnatrix é uma plataforma online que fornece aos alunos uma forma estruturada de estudar e avaliar os seus conhecimentos. Combina:

- **Livros Digitais:** Os alunos podem aceder a materiais de aprendizagem online.

- **Sistema de testes:** Uma plataforma de avaliação baseada em perguntas do exame teórico do IMT calculando as respostas incorrectas e um índice de preparação.

- **Análise de desempenho:** A plataforma ajuda os alunos a identificar as áreas fracas e a concentrar-se na melhoria.

- **Aulas de e-learning:** Inclui aulas em vídeo, exercícios interactivos e feedback em tempo real.

### Gescola

O Gescola é um sistema de gestão escolar que permite às instituições acompanhar os alunos, o progresso académico, as finanças e as operações diárias. As principais caraterísticas incluem:

- **Gestão de Registos de Alunos:** Armazena e organiza a informação dos alunos.

- **Controlo de assiduidade:** Monitoriza a presença dos alunos nas aulas.

- **Gestão financeira:** Trata das propinas, facturas e pagamentos dos alunos.

- **Marcação de exames e resultados:** Gere as datas dos testes e regista as notas dos alunos.

---

## Visão geral da aplicação

### Projeto 1 (Inspirado pelo Pugnatrix)

O Projeto 1 é uma plataforma interativa de aprendizado e avaliação, onde os alunos podem estudar com livros online, fazer testes práticos e acompanhar o seu progresso. A plataforma oferece:

- Uma biblioteca de livros digitais com conteúdo interativo.
- Um motor de teste que calcula as respostas incorrectas e fornece um índice de preparação.
- Aulas de e-learning online com vídeos ou aulas gravadas e questionários interativos.
- Acompanhamento e análise do desempenho do utilizador.

### Projeto 2 (Inspirado por Gescola)

O Projeto 2 é um sistema de gestão escolar que facilita o trabalho dos administradores na gestão de dados dos alunos, presença, exames e registros financeiros. As principais funções incluem:

- Uma base de dados de alunos que contém detalhes pessoais e académicos.
- Um sistema de controlo de assiduidade.
- Um módulo financeiro para gerir pagamentos e faturas.
- Programação de exames e gestão de resultados.

---

## Requisitos do sistema e repartição funcional

### Componentes do sistema do Projeto 1

#### Gestão de utilizadores

| Campo | Tipo | Descrição |
|-----------------|-------------|-----------------------------------------|
| ID do utilizador | UUID | Identificador único para cada utilizador
| Nome | String | Nome completo do utilizador |
| Email | String | Endereço de email do utilizador
| Palavra-passe | String (Hash) | Palavra-passe armazenada de forma segura
| Função | Enum | Define a função (Aluno/Professor/Administrador) |
| Assinatura | Enum | Níveis de acesso Free/Premium |
| Imagem do perfil | String (URL) | Link para a imagem do perfil |

#### Biblioteca digital

| Campo | Tipo | Descrição |
|---------|------|---------------------------------|
| ID do livro | UUID | Identificador único para cada livro |
| Título | String | Título do livro |
| Autor | String | Autor do livro |
| Assunto | String | Categoria do assunto |
Ano | Inteiro | Ano de publicação | Formato | Enum | PDF | PDF
| Formato | Enum | PDF, ePub, etc.                 |

#### Sistema de teste

| Campo | Tipo | Descrição |
|------------|--------|----------------------------------|
| ID do teste | UUID | Identificador único para cada teste
| ID do aluno | UUID | Identificador associado ao aluno |
Perguntas | Array | Lista de perguntas | Respostas | Array | Respostas enviadas
| Tempo restante | Inteiro | Tempo restante para o teste acabar |
| Respostas | Array | Respostas enviadas |
| Pontuação | Float | Pontuação do teste calculada |
| Índice de preparação | Float | Nível de preparação baseado no desempenho |

#### Aulas on-line

| Campo | Tipo | Descrição |
|-----------|------|---------------------------------|
| ID da turma | UUID | Identificador único da turma |
| ID do professor | UUID | Identificador associado do professor
| IDs de alunos | Array | Lista de alunos inscritos
| Materiais | Array | Links para vídeos, PDFs, etc.   |
| Atribuições | Array | Lista de atribuições e questionários |

---

### Componentes do sistema do Projeto 2

#### Gestão de Alunos

| Campo | Tipo | Descrição |
|----------|------|---------------------------------|
| ID do aluno | UUID | Identificador único do aluno |
| Nome | String | Nome completo | Data de nascimento
| Data de nascimento | Data | Data de nascimento do aluno |
| Email | String | Email de contacto |
| Classes inscritas | Array | Lista de cursos inscritos |
| Detalhes do encarregado de educação | Objeto | Informação de contacto dos pais/encarregados de educação |

#### Gestão de aulas e assiduidade

| Campo | Tipo | Descrição |
|----------|------|---------------------------------|
| ID da turma | UUID | Identificador único da turma |
| Nome do curso | String | Nome do curso |
| ID do professor | UUID | Identificador do instrutor |
| IDs de alunos | Array | Alunos matriculados |
| Registos de assiduidade | Objeto | Registos de assiduidade dos alunos |

#### Gestão financeira

| Campo | Tipo | Descrição |
|-----------|------|---------------------------|
| ID da conta | UUID | Identificador único da conta
| ID do aluno | UUID | Identificador de aluno associado |
| Facturas | Array | Registos de pagamento |
| Taxas pendentes | Float | Saldo não pago |

#### Exames e resultados

| Campo | Tipo | Descrição |
|---------|------|-----------------------------|
| ID do exame | UUID | Identificador único do exame |
| ID do curso | UUID | Curso associado
| ID do aluno | UUID | Aluno que está a fazer o exame
| Pontuação | Float | Nota final ou pontuação |


Segue-se uma tabela que explica os diferentes tipos de dados utilizados no projeto:  
 

| **Tipo de dados**  | **Descrição** | **Exemplo** |
|---------------|---------------|------------|
| **UUID (Universally Unique Identifier)** | Um identificador único de 128 bits utilizado para os registos, garantindo a unicidade entre sistemas. | `550e8400-e29b-41d4-a716-446655440000` |
| **String** | Uma sequência de caracteres, utilizada para nomes, mensagens de correio eletrónico, etc. | `"John Doe"`, `"johndoe@example.com"` |
| **Inteiro** | Um número inteiro, utilizado para identificações, contagens, etc. | `42`, `2024` |
| **Float** | Um número decimal, utilizado para pontuações, preços, etc. | `4.5`, `99.99` |
| **Boolean** | Um valor que pode ser `true` ou `false`, utilizado para definições como “isAdmin”. | `true`, `false` |
| **Array (List)** | Uma coleção de valores múltiplos, utilizada para armazenar listas de alunos, cursos, etc. | `["Math", "Science", "History"]` |
| **Objeto** | Uma coleção de pares key-value, frequentemente utilizada para armazenar dados estruturados como perfis de utilizador. | `{"name": "John", "age": 25, "email": "john@example.com"}` |
| **Enum (Enumeration)** | Uma lista predefinida de valores possíveis, utilizada para funções, estados, etc. | `Role = ["Student", "Teacher", "Admin"]` |
| **Data** | Um ponto específico no tempo, utilizado para datas de nascimento, datas de testes, etc. | `"2025-03-20T15:30:00Z"` |

---

## Considerações sobre a stack técnica e o desenvolvimento

Para desenvolver este projeto de forma eficiente, recomenda-se a seguinte stack:

### Frontend:

- **React.js** (para uma UI dinâmica e interativa)

- **Next.js** (para renderização do lado do servidor e otimização de desempenho)

- **Tailwind CSS** (para um design moderno e responsivo)

### Backend:

- **Node.js com Express.js** (para lidar com pedidos de API)

- **Django ou Flask (alternativa para backend baseado em Python)**

### Base de dados:

- **PostgreSQL** (para dados estruturados e relacionais)

- **MongoDB (opcional)** (para tratamento de dados não estruturados)

### Autenticação e segurança:

- **JWT (JSON Web Token)** (para autenticação segura)

- **OAuth2 / Firebase Auth** (para logins sociais)

- **bcrypt ou Argon2** (para hashing de palavras-passe)

### Nuvem e hospedagem:

- **AWS / Google Cloud / Vercel** (para implantação escalável)

- **Firebase** (para base de dados e autenticação em tempo real)

### Ferramentas adicionais:

- **DDEV** (para desenvolvimento local)

- **Docker** (para desenvolvimento em containers)

- **Git** (para controlo de versões e colaboração)

- **CI/CD (GitHub Actions / Jenkins)** (para implantação automatizada)

- **Redis** (para armazenar em cache dados frequentemente acedidos)
  
---

## Desenvolvimento Futuro

Atualmente, a prioridade é desenvolver o **Projeto 1**, com o **Projeto 2** a seguir. Em breve virá mais atualizações.