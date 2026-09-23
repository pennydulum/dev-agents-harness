---
title: MSW Best Practices
source: MSW Docs + Internal
url: https://mswjs.io/docs/best-practices
authority: High
version: 1.0
last_verified: 2026-09-23
---

# MSW Best Practices

## 1. One Handler Set
- **Share handlers** between **Storybook** and **Vitest**.
- **Never** maintain separate mocks for the same API.

## 2. GraphQL Operation Routing
- Use **operation names** (not URLs) for GraphQL:
  ```typescript
  graphql.query('GetUser', ({ variables }) => {
    return { data: { user: { id: variables.id, name: 'Mock User' } } };
  });
  ```

## 3. Stateful Mocks
- Use **in-memory stores** for multi-step flows:
  ```typescript
  let users = new Map<number, User>();

  graphql.mutation('CreateUser', ({ variables }) => {
    const user = { id: Date.now(), ...variables };
    users.set(user.id, user);
    return { data: { createUser: user } };
  });

  graphql.query('GetUser', ({ variables }) => {
    return { data: { user: users.get(variables.id) } };
  });
  ```

## 4. Reset Between Tests
- **Vitest**: Reset handlers in `afterEach`:
  ```typescript
  afterEach(() => {
    server.resetHandlers();
    users.clear(); // Reset state
  });
  ```
- **Storybook**: Reset in `beforeEach` of test files.

## 5. Unhandled Requests
- **Fail tests** on unhandled requests (default behavior).
- **Log warnings** for debugging:
  ```typescript
  server.on('request:start', (req) => {
    console.warn('Unhandled request:', req.method, req.url);
  });
  ```

## 6. Error Mocking
- Mock **error responses** (e.g., 404, 500):
  ```typescript
  graphql.query('GetUser', ({ variables }) => {
    if (variables.id === 999) {
      return new Error('User not found');
    }
    return { data: { user: { id: variables.id, name: 'Mock User' } } };
  });
  ```

## 7. Network Errors
- Use `networkError` for network-level failures:
  ```typescript
  http.get('/api/users', () => {
    return networkError('Failed to fetch');
  });
  ```

## Anti-Patterns
- **Mocking at the client level** (e.g., mocking Apollo Client) **and** MSW simultaneously.
- **Hardcoding responses** without considering variables.
- **Not resetting state** between tests (leads to flakiness).