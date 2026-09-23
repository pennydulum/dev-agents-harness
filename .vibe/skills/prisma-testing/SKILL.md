---
name: Prisma Database Testing
description: Test database constraints, migrations, and queries using disposable databases (Neon/Docker).
user-invocable: true
---

## Objective
Test **database logic** (constraints, migrations, queries) in isolation using **disposable databases**.

## Procedure
1. **Set Up Disposable DB**:
   - **Neon**: Use a **branch** for each test run.
     ```bash
     # Create a Neon branch for testing
     psql -h <neon-host> -U <user> -d <db> -c "CREATE DATABASE test_db;"
     ```
   - **Docker**: Spin up a **Postgres container**.
     ```bash
     docker run --name test-postgres -e POSTGRES_PASSWORD=test -p 5433:5432 -d postgres
     ```

2. **Apply Migrations**:
   - Run `prisma migrate deploy` or `prisma db push` before tests.
   - Example (in `beforeAll`):
     ```typescript
     beforeAll(async () => {
       await exec('prisma migrate deploy --schema=./prisma/test.schema.prisma');
     });
     ```

3. **Seed Test Data**:
   - Use **deterministic fixtures** (no randomness unless seeded).
   - Example:
     ```typescript
     beforeEach(async () => {
       await prisma.user.create({ data: { id: 1, email: 'test@example.com' } });
     });
     ```

4. **Test Constraints**:
   - **Unique constraints**: Attempt to create duplicate records.
   - **Foreign keys**: Test cascading deletes/updates.
   - **Nullability**: Test `null` vs. required fields.
   - Example:
     ```typescript
     test('unique email constraint', async () => {
       await expect(
         prisma.user.create({ data: { id: 2, email: 'test@example.com' } })
       ).rejects.toThrow('Unique constraint failed');
     });
     ```

5. **Test Transactions**:
   - Use `prisma.$transaction` to test atomicity.
   - Example:
     ```typescript
     test('transaction rollback on failure', async () => {
       await expect(
         prisma.$transaction([
           prisma.user.create({ data: { id: 1, email: 'a@example.com' } }),
           prisma.user.create({ data: { id: 1, email: 'b@example.com' } }), // Duplicate ID
         ])
       ).rejects.toThrow();
       const users = await prisma.user.findMany();
       expect(users.length).toBe(0); // Rollback
     });
     ```

6. **Clean Up**:
   - **Neon**: Delete the branch after tests.
   - **Docker**: Stop/remove the container.

## Rules
- **Never** test against a **shared dev database**.
- **Never** commit **production data** as fixtures.
- **Always** reset the database between tests.
- **Use** `prisma.$executeRaw` for raw SQL if needed.

## Output Format
```markdown
### Prisma Test: [Scenario]
- **Database**: `[Neon/Docker]`.
- **Migrations**: `[Applied/Not Applied]`.
- **Fixtures**: `[Deterministic/Random]`.
- **Constraints Tested**: `[Unique/Foreign Key/Nullability/Transactions]`.
- **Cleanup**: `[Automatic/Manual]`.
```