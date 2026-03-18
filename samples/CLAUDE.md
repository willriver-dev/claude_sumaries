# Project: E-Commerce Platform

## Core Principles
**IMPORTANT**: Whenever you write code, it MUST follow SOLID design principles.
Never write code that violates these principles. If you do, you will be asked to refactor it.

## Development Workflow
1. Create and checkout feature branch: `feature/[brief-description]`
2. Write comprehensive tests for all new functionality
3. Compile code and run all tests before committing: `npm run lint && npm test`
4. Write detailed commit messages explaining changes and rationale
5. Commit all changes to the feature branch

## Architecture Overview
- Frontend: Next.js 14 with TypeScript and Tailwind CSS
- State Management: Zustand (client), React Query (server)
- Backend: Node.js with Express and Prisma ORM
- Database: PostgreSQL
- Testing: Vitest (unit), Playwright (E2E)
- Authentication: NextAuth.js with JWT

## Code Standards
- TypeScript strict mode for all new code
- Follow existing component structure in `src/components/[Feature]/[ComponentName].tsx`
- API routes follow RESTful conventions in `src/app/api/`
- Tailwind utilities preferred; custom CSS only when necessary
- Use React Server Components by default, `"use client"` only when needed

## Naming Conventions
- Components: PascalCase (`ProductCard.tsx`)
- Utilities/hooks: camelCase (`useCartItems.ts`, `formatCurrency.ts`)
- API routes: kebab-case (`/api/order-history`)
- Database tables: snake_case (`order_items`)
- Environment variables: UPPER_SNAKE_CASE (`DATABASE_URL`)

## Quality Gates
- All code must compile without warnings
- Test coverage must remain above 80%
- ESLint and Prettier must pass without errors
- No `any` type usage — use `unknown` with type guards instead

## File Organization
```
src/
  components/[Feature]/[ComponentName].tsx
  app/api/[resource]/route.ts
  lib/[category]/[utility].ts
  types/[domain].ts
  hooks/use[Feature].ts
```

## Important Notes
- Never commit `.env` files or secrets to version control
- Use parameterized queries — never concatenate user input into SQL
- All user-facing text must support i18n via `next-intl`
- Prefer vectorized database operations over N+1 queries
