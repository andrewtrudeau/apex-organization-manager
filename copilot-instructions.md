# Apex Development Instructions

Apex is a multi-tenant workforce and contracting management platform.

## Technology

- TypeScript
- pnpm
- Turborepo
- React + Vite for web
- React Native + Expo for mobile
- Hono + Node.js for API
- PostgreSQL
- Drizzle ORM
- TanStack Query
- Zod only where runtime validation is actually required
- Vitest for testing

## Architecture

Use a modular monorepo.

apps/
web/
mobile/
api/

packages/
db/
api-client/
shared/

The database schema is defined with Drizzle.

Prefer deriving TypeScript types from Drizzle rather than manually duplicating database types.

Do not create Mongoose models.

Do not introduce MongoDB.

The backend is responsible for authentication, authorization, validation,
business rules, database access, transactions, and security.

The frontend and mobile applications must never connect directly to PostgreSQL.

## Development philosophy

Apex is currently in foundation/setup phase.

Do NOT implement business features unless explicitly requested.

Prioritize:

1. Correct architecture
2. Type safety
3. Simple code
4. Clear separation of concerns
5. Testability
6. Maintainability

Avoid premature abstractions.

Do not introduce microservices.

Do not add unnecessary dependencies.

After making changes, run the relevant typecheck, lint, and test commands
and fix errors before declaring the task complete.

When a task is ambiguous, explain the ambiguity before making major architectural
decisions.
