---
name: MSW Handlers
description: Create and maintain shared MSW handlers for GraphQL/REST APIs. Use for mocking network requests in tests and Storybook.
user-invocable: true
---

## Objective
Create **shared MSW handlers** for GraphQL/REST APIs to enable consistent mocking across Vitest and Storybook.

## Procedure
1. **Inspect the API**:
   - Identify the **GraphQL schema** or **REST endpoints** to mock.
   - Note **operation names** (for GraphQL) or **paths/methods** (for REST).

2. **Create Handlers**:
   - For **GraphQL**: Use `graphql.query()` or `graphql.mutation()` with operation names.
     ```typescript
     // Example: .vibe/skills/msw-handlers/examples/graphql.ts
     import { graphql } from 'msw';

     export const handlers = [
       graphql.query('GetUser', ({ variables }) => {
         return {
           data: {
             user: {
               id: variables.id,
               name: 'Mock User',
             },
           },
         };
       }),
     ];
     ```
   - For **REST**: Use `http.get()`, `http.post()`, etc.
     ```typescript
     import { http } from 'msw';

     export const handlers = [
       http.get('/api/users/:id', ({ params }) => {
         return new Response(JSON.stringify({ id: params.id, name: 'Mock User' }));
       }),
     ];
     ```

3. **Stateful Mocks** (for multi-step flows):
   - Use an **in-memory store** (e.g., `Map`, `Array`) to track state.
   - Reset state between tests using `beforeEach` or `afterEach`.

4. **Integrate with Tests/Storybook**:
   - **Vitest**: Import handlers in `setupFiles` or per-test.
     ```typescript
     import { setupServer } from 'msw/node';
     import { handlers } from './msw-handlers';

     const server = setupServer(...handlers);
     beforeAll(() => server.listen());
     afterEach(() => server.resetHandlers());
     afterAll(() => server.close());
     ```
   - **Storybook**: Add handlers to `.storybook/preview.ts`.
     ```typescript
     import { setupWorker } from 'msw';
     import { handlers } from '../msw-handlers';

     const worker = setupWorker(...handlers);
     worker.start();
     ```

5. **Error Handling**:
   - Mock **error responses** (e.g., 404, 500) to test error paths.
   - Use `networkError` for network-level failures.

## Rules
- **One handler per operation** (GraphQL) or **endpoint + method** (REST).
- **Never** mock the same API in multiple ways (e.g., MSW + Apollo mocks).
- **Reset handlers** between tests to avoid state leakage.
- **Log unhandled requests** in tests (fail if unexpected).

## Output Format
```markdown
### MSW Handlers for [API]
- **GraphQL Operations**: `[List of operations]`.
- **REST Endpoints**: `[List of endpoints]`.
- **Stateful Mocks**: `[Yes/No]` — `[Description]`.
- **Integration**:
  - Vitest: `[setup-file]`.
  - Storybook: `[preview-file]`.
- **Unhandled Requests**: `[Fail/Log/Warn]`.
```