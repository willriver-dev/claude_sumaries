# Document Feature Command

Generate comprehensive documentation for: $ARGUMENTS

## Analysis Phase
1. Find all code files related to $ARGUMENTS
2. Identify if feature is frontend, backend, or full-stack
3. Read existing documentation patterns in `/docs`

## Developer Documentation
Create `docs/dev/{feature-name}-implementation.md`:
- Architecture overview
- API endpoints and contracts
- Data models and schemas
- Key implementation decisions
- Dependencies and integrations
- Testing approach

## User Documentation
Create `docs/user/how-to-{feature-name}.md`:
- Feature overview in non-technical language
- Step-by-step instructions with numbered steps
- `[Screenshot: {step-description}]` placeholders for each key step
- Common issues and troubleshooting
- Related features cross-reference

## Cross-References
- Link dev docs to user docs and vice versa
- Link to related existing documentation
