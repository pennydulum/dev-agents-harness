---
name: Playwright E2E Testing
description: Write and maintain Playwright E2E tests for critical user journeys, auth, and tenant isolation.
user-invocable: true
---

## Objective
Write **deterministic, isolated E2E tests** for high-value user journeys (auth, tenant isolation, critical CRUD).

## Procedure
1. **Identify Critical Journeys**:
   - Auth flows (e.g., Okta PKCE).
   - Tenant isolation (e.g., "Tenant A cannot access Tenant B’s data").
   - Cross-page workflows (e.g., "Create Project → Add Task → Verify Task List").

2. **Write the Test**:
   - Use **semantic locators** (e.g., `page.getByRole('button', { name: 'Login' })`).
   - Avoid **CSS/XPath selectors** tied to styling.
   - **Isolate browser contexts** per test:
     ```typescript
     test('tenant isolation', async ({ browser }) => {
       const tenantA = await browser.newContext();
       const tenantB = await browser.newContext();
       // Test cross-tenant access...
     });
     ```

3. **Auth Setup**:
   - Use **test users** (not real user accounts).
   - Store credentials in **environment variables** (never in code).
   - Example:
     ```typescript
     const { E2E_USER_EMAIL, E2E_USER_PASSWORD } = process.env;
     await page.fill('#email', E2E_USER_EMAIL);
     await page.fill('#password', E2E_USER_PASSWORD);
     ```

4. **Tenant Isolation**:
   - Log in as **Tenant A**, verify access to **Tenant A’s data**. 
   - Log in as **Tenant B**, verify **no access** to Tenant A’s data.
   - Example:
     ```typescript
     test('Tenant A cannot access Tenant B data', async ({ page }) => {
       await loginAsTenantA(page);
       await page.goto('/tenant-b-data');
       await expect(page.getByText('Access Denied')).toBeVisible();
     });
     ```

5. **Evidence on Failure**:
   - Enable **traces, videos, and screenshots** in `playwright.config.ts`:
     ```typescript
     export default defineConfig({
       use: {
         trace: 'on-first-retry',
         video: 'retain-on-failure',
         screenshot: 'only-on-failure',
       },
     });
     ```

## Rules
- **Never** test third-party websites (mock external dependencies).
- **Never** use `page.waitForTimeout()` (use `page.waitForSelector()` or `expect(locator).toBeVisible()`).
- **Never** share browser contexts between tests.
- **Always** clean up test data (e.g., delete test users/projects).

## Output Format
```markdown
### Playwright E2E Test: [Journey]
- **Journey**: `[Description]`.
- **Auth**: `[Test User/Real User]` — `[Email/SSO]`.
- **Tenant Isolation**: `[Yes/No]` — `[Description]`.
- **Locators**: `[Semantic/CSS/XPath]`.
- **Evidence**: `[Trace/Video/Screenshot]`.
- **Flakiness**: `[None/Quarantined]` — `[Reason]`.
```