# NLW Agents - Server

Servidor Fastify para gerenciamento de salas (rooms) utilizando PostgreSQL, Drizzle ORM e validação com Zod.

## Tecnologias Utilizadas

- **Node.js** com TypeScript nativo (experimental strip types)
- **Fastify:** Framework web rápido para Node.js.
- **Drizzle ORM** ORM para TypeScript focado em segurança e performance.
- **PostgreSQL:** Banco de dados relacional.
- **Zod:** Validação de esquemas para TypeScript.
- **drizzle-seed:** Seed e reset de banco de dados.
- **Biome:** Linter e formatter.

## Padrão de Projeto

- **Modularização:** Separação clara entre rotas HTTP, configuração de ambiente, banco de dados e schemas.
- **Validação:** Uso de Zod para validação de variáveis de ambiente e payloads.
- **Migrations:** Gerenciadas via Drizzle ORM.
- **Seed:** População do banco com dados fake usando drizzle-seed.

## Setup e Configurações

### Pré-requisitos

- Node.js (versão com suporte a `--experimental-strip-types`)
- Docker e Docker Compose

### 1. Clone o repositório

```sh
git clone <url-do-repositorio>
cd server
```

### 2. Configure o banco de dados

```sh
docker-compose up -d
```

### 3. Configure as variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
PORT=3333
DATABASE_URL=postgres://docker:docker@localhost:5432/agents
```

### 4. Instale as dependências

```sh
npm install
```

### 5. Execute as migrações do banco

```sh
npx drizzle-kit migrate
```

### 6. (Opcional) Popule o banco com dados de exemplo

```sh
npm run db:seed
```

### 7. Execute o projeto

**Desenvolvimento**

```sh
npm run dev
```

**Produção**

```sh
npm run dev
```

## Scripts Disponíveis

- `npm ru dev` - Executa o servidor em modo de desenvolvedor com hoy reload
- `npm start` - Executa o servidor em modo de produção
- `nps run db:seed` - Popula o banco de dados com dados de exemplo

## Endpoints

A API estará disponível em `http://localhost:3333`

- `GET /health` - Health check
- `GET /rooms` - Lista todas as salas

---

> Projeto desenvolvido com foco em boas práticas de TypeScript, validação e organização de código.
