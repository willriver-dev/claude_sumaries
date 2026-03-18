# New Feature Command

Implement the following feature: $ARGUMENTS

## Before Coding
1. Read the design document in `docs/design/` if one exists for this feature
2. Read `CLAUDE.md` to review project conventions
3. Identify which existing components/modules this feature touches

## Implementation Process
1. Create feature branch: `feature/{feature-name}`
2. Start with data models and types in `src/types/`
3. Implement backend API routes in `src/app/api/`
4. Build frontend components in `src/components/{Feature}/`
5. Write tests alongside each layer
6. Run `npm run lint && npm test` before committing

## Quality Checks
- Follow SOLID principles — single responsibility per file
- No `any` types — use proper TypeScript generics or `unknown` with type guards
- All user inputs must be validated with Zod schemas
- Error states must have user-friendly messages
- Loading states must be handled for all async operations

## Commit Strategy
- Commit after each logical unit (model, API, component, tests)
- Each commit must leave the app in a working state
- Use descriptive commit messages: `feat: add {what} for {why}`
