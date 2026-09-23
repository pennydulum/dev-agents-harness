---
name: Flaky Test Triage
description: Diagnose, quarantine, and fix flaky tests. Use when a test passes locally but fails in CI.
user-invocable: true
---

## Objective
**Eliminate flakiness** by identifying root causes and enforcing quarantine policies.

## Procedure
1. **Reproduce the Flake**:
   - Run the test **10+ times** locally to confirm flakiness.
   - Example:
     ```bash
     for i in {1..10}; do pnpm test --grep "flaky-test"; done
     ```

2. **Isolate the Cause**:
   - **Test Issue**: Race condition, async/await mismatch, shared state.
   - **Environment Issue**: Missing dependency, timeouts, resource limits.
   - **Infrastructure Issue**: CI runner instability, network latency.
   - **Dependency Issue**: Third-party API downtime, rate limits.

3. **Quarantine the Test**:
   - Move the test to a **quarantine suite** (e.g., `tests/quarantine/`).
   - Skip in blocking CI gates:
     ```yaml
     # .github/workflows/ci.yml
     - name: Run Tests
       run: pnpm test --exclude="**/quarantine/*"
     ```

4. **Fix the Root Cause**:
   - **Race conditions**: Use `await` properly, add `test.serial` (Playwright).
   - **Shared state**: Reset between tests (e.g., `beforeEach`).
   - **Timeouts**: Increase timeouts or mock slow dependencies.
   - **Environment**: Pin dependency versions, use deterministic data.

5. **Track in Backlog**:
   - Create a **GitHub issue** labeled `flaky-test` with:
     - Test name/file.
     - Failure frequency.
     - Root cause hypothesis.
     - Quarantine date.

6. **Re-enable**:
   - After fixing, run the test **50+ times** in CI before re-enabling.

## Rules
- **Never** silently retry flaky tests in blocking gates.
- **Never** ignore quarantined tests (assign ownership).
- **Always** document the root cause and fix.

## Output Format
```markdown
### Flaky Test Triage: [Test Name]
- **File**: `[test-file]:[line]`.
- **Failure Rate**: `[X/10 runs]`.
- **Root Cause**: `[Test/Environment/Infrastructure/Dependency]`.
- **Quarantine Date**: `[YYYY-MM-DD]`.
- **Fix**: `[Description]`.
- **Re-enabled**: `[Yes/No]` — `[Date]`.
```