---
name: Test-Driven Development (TDD)
description: Write failing tests before implementation, then refactor. Use for new features, bug fixes, and refactors.
user-invocable: true
---

## Objective
Implement a feature or fix using the **TDD cycle**: Red → Green → Refactor.

## Procedure
1. **Red**: Write a failing test that defines the desired behavior.
   - Use `it('should...', () => { ... })` or `test('...', () => { ... })`.
   - Assert the **expected outcome** (not implementation details).
   - Run the test to confirm it fails (red).

2. **Green**: Write the **minimal code** to make the test pass.
   - Avoid over-engineering; focus on passing the test.
   - Run the test to confirm it passes (green).

3. **Refactor**: Improve the code **without changing behavior**.
   - Remove duplication.
   - Improve readability.
   - Re-run tests to ensure they still pass.

4. **Repeat**: Add more test cases for edge cases, then refactor.

## Rules
- **Never** write tests after implementation (unless fixing a bug in existing code).
- **Never** mock internal implementation details (e.g., mocking a function inside the same module).
- **Prefer** behavior-focused tests over implementation-focused tests.
- **Isolate** tests: No shared state between tests.

## Output Format
```markdown
### TDD Cycle for [Feature/Bug]
1. **Red**: Test `[test-file]:[line]` fails with `[error]`.
   - Expected: `[behavior]`.
   - Actual: `[behavior]`.

2. **Green**: Implemented `[code-change]` in `[file]:[line]`.
   - Test now passes.

3. **Refactor**: Improved `[aspect]` in `[file]:[line]`.
   - All tests still pass.

**Residual Risk**: [None/Low/Medium/High] — [Explanation].
```