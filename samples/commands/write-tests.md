# Write Tests Command

Write comprehensive tests for: $ARGUMENTS

## Testing Strategy
1. **Happy Path**: Valid inputs, expected outputs, normal user flows
2. **Error Handling**: Invalid inputs, authentication failures, edge cases
3. **Boundary Values**: Empty arrays, null values, max limits

## Standards
- Read existing test files in `src/__tests__/` to match our testing style
- Use Vitest with React Testing Library for component tests
- Use MSW (Mock Service Worker) for API mocking — never mock fetch directly
- Each test must have a clear, descriptive name explaining the scenario

## Test Structure
Place tests in `src/__tests__/{module}/{feature}.test.ts`

```
describe('{Feature}', () => {
  describe('when {scenario}', () => {
    it('should {expected behavior}', () => {
      // Arrange → Act → Assert
    });
  });
});
```

## Output
- Run `npm test -- --run {test-file}` after writing to verify all tests pass
- Report coverage for the tested module
