# Playwright Verified Reference

All information verified against official Playwright documentation at https://playwright.dev/docs/ on 2026-04-15. Use this to cross-check code snippets and technical claims in LinkedIn posts.

**CRITICAL**: Always WebFetch the relevant Playwright docs page to verify any code or API not covered here. This file covers the most common topics but is not exhaustive.

---

## 1. Fixtures (Dependency Injection)

**Source:** https://playwright.dev/docs/test-fixtures

**Correct API:**
```typescript
import { test as base } from '@playwright/test';

type MyFixtures = {
  loginPage: LoginPage;
  dashboardPage: DashboardPage;
};

export const test = base.extend<MyFixtures>({
  loginPage: async ({ page }, use) => {
    const loginPage = new LoginPage(page);
    await use(loginPage);
  },
  dashboardPage: async ({ page }, use) => {
    const dashboardPage = new DashboardPage(page);
    await use(dashboardPage);
  },
});
```

**Key facts:**
- Fixtures are on-demand (only requested ones initialize)
- Composable: fixtures can depend on other fixtures
- Two scopes: test-scoped (per-test isolation) and worker-scoped (shared resources)
- Auto-fixture: `{ auto: true }` for setup every test requires
- Boxing: `{ box: true }` to reduce report clutter
- Preferred over beforeEach/afterEach hooks for encapsulation and reusability

---

## 2. Locator Hierarchy

**Source:** https://playwright.dev/docs/locators

**Complete priority (recommended order):**
1. `page.getByRole('button', { name: 'Submit' })` - ARIA role + accessible name
2. `page.getByLabel('Email address')` - Form controls by label text
3. `page.getByPlaceholder('Enter your email')` - Inputs by placeholder
4. `page.getByText('Welcome back')` - Elements by text content (supports regex)
5. `page.getByAltText('Company logo')` - Images by alt text
6. `page.getByTitle('Close dialog')` - Elements by title attribute
7. `page.getByTestId('submit-button')` - Elements by data-testid attribute

**Fallback methods:**
- `page.locator('css=selector')` - CSS selectors
- `page.locator('xpath=//div')` - XPath (last resort)

**Key facts:**
- All locators have built-in auto-waiting and retry capabilities
- Available on Page, Locator, and FrameLocator classes
- Chainable: `page.getByRole('listitem').filter({ hasText: 'Product' })`
- `getByRole` is preferred because it tests accessibility, not implementation

---

## 3. Test Sharding

**Source:** https://playwright.dev/docs/test-sharding

**CLI command:**
```bash
npx playwright test --shard=1/4
npx playwright test --shard=2/4
npx playwright test --shard=3/4
npx playwright test --shard=4/4
```

**Report merging:**
```typescript
// playwright.config.ts
export default defineConfig({
  reporter: process.env.CI ? 'blob' : 'html',
});
```

```bash
# Merge shard reports
npx playwright merge-reports --reporter html ./all-blob-reports
```

**Key facts:**
- Use `fullyParallel: true` for balanced test-level sharding
- Without `fullyParallel`, shards at file level (can be imbalanced)
- Each shard runs independently on separate machines
- Blob reporter captures all data needed for merging

---

## 4. Authentication / Login Once Pattern

**Source:** https://playwright.dev/docs/auth

**Project dependencies config:**
```typescript
// playwright.config.ts
export default defineConfig({
  projects: [
    { name: 'setup', testMatch: /.*\.setup\.ts/ },
    {
      name: 'chromium',
      use: {
        ...devices['Desktop Chrome'],
        storageState: 'playwright/.auth/user.json',
      },
      dependencies: ['setup'],
    },
  ],
});
```

**Setup file:**
```typescript
// tests/auth.setup.ts
import { test as setup, expect } from '@playwright/test';

const authFile = 'playwright/.auth/user.json';

setup('authenticate', async ({ page }) => {
  await page.goto('https://your-app.com/login');
  await page.getByLabel('Email').fill('user@example.com');
  await page.getByLabel('Password').fill('password');
  await page.getByRole('button', { name: 'Sign in' }).click();
  await page.waitForURL('https://your-app.com/dashboard');
  await page.context().storageState({ path: authFile });
});
```

**Key facts:**
- Setup project runs first, saves browser state to JSON
- All dependent projects reuse the saved state
- Works when tests can share the same account
- For tests that modify shared state, use "one account per parallel worker" pattern
- Add `playwright/.auth/` to `.gitignore`

---

## 5. Trace Viewer

**Source:** https://playwright.dev/docs/trace-viewer

**Configuration:**
```typescript
// playwright.config.ts
export default defineConfig({
  use: {
    trace: 'on-first-retry', // or 'on', 'off', 'retain-on-failure', 'on-all-retries'
  },
});
```

**CLI access:**
```bash
npx playwright show-trace trace.zip
```

**Online viewer:** trace.playwright.dev

**Captured data:**
- Actions tab: locators used, timing, DOM snapshots before/after
- Screenshots: filmstrip timeline of execution
- Snapshots: complete DOM states at each step
- Source: relevant test source code lines
- Console: browser console logs
- Network: all HTTP requests and responses
- Errors: failure messages with timeline context
- Metadata: browser type, viewport, test duration

---

## 6. Visual Regression / Screenshot Testing

**Source:** https://playwright.dev/docs/test-snapshots

**API:**
```typescript
// Full page screenshot comparison
await expect(page).toHaveScreenshot();

// Named screenshot
await expect(page).toHaveScreenshot('landing-page.png');

// Element screenshot
await expect(page.getByRole('main')).toHaveScreenshot();

// With options
await expect(page).toHaveScreenshot({
  maxDiffPixels: 100,
  mask: [page.getByRole('img', { name: 'avatar' })],
});
```

**Key facts:**
- First run captures screenshots, saves as golden files
- Subsequent runs compare against baseline
- Platform-specific baselines (different rendering per OS)
- `maxDiffPixels` for pixel tolerance using pixelmatch
- `mask` option to hide dynamic elements (avatars, timestamps)
- `--update-snapshots` flag to regenerate baselines
- `stylePath` option for custom CSS to hide dynamic content

---

## 7. Route Interception (Aborting Requests)

**Source:** https://playwright.dev/docs/api/class-page#page-route

**API:**
```typescript
// Block all images
await page.route('**/*.{png,jpg,jpeg,gif,svg}', (route) => route.abort());

// Block by regex
await page.route(/(\.png$)|(\.jpg$)/, (route) => route.abort());

// Mock API response
await page.route('**/api/users', async (route) => {
  await route.fulfill({
    status: 200,
    contentType: 'application/json',
    body: JSON.stringify([{ id: 1, name: 'Test User' }]),
  });
});

// Modify request
await page.route('**/api/data', async (route) => {
  const response = await route.fetch();
  const json = await response.json();
  json.modified = true;
  await route.fulfill({ response, json });
});
```

**Key facts:**
- Matching requests stall until continued, fulfilled, or aborted
- Pattern-based URL matching (glob or regex)
- `route.abort()` cancels the request
- `route.continue()` passes through normally
- `route.fulfill()` returns a mocked response
- `route.fetch()` makes the real request, lets you modify response

---

## 8. Data-Driven Testing / Parameterization

**Source:** https://playwright.dev/docs/test-parameterize

**Array-based parameterization:**
```typescript
const people = ['Alice', 'Bob', 'Charlie'];

for (const name of people) {
  test(`testing with ${name}`, async ({ page }) => {
    await page.goto(`/profile/${name}`);
    await expect(page.getByRole('heading')).toContainText(name);
  });
}
```

**Project-based parameterization:**
```typescript
// playwright.config.ts
export default defineConfig({
  projects: [
    {
      name: 'staging',
      use: { baseURL: 'https://staging.example.com' },
    },
    {
      name: 'production',
      use: { baseURL: 'https://production.example.com' },
    },
  ],
});
```

**CSV data source:**
```typescript
import fs from 'fs';
import path from 'path';
import { parse } from 'csv-parse/sync';
import { test } from '@playwright/test';

const records = parse(fs.readFileSync(path.join(__dirname, 'data.csv')), {
  columns: true,
  skip_empty_lines: true,
});

for (const record of records) {
  test(`test with ${record.name}`, async ({ page }) => {
    // test logic using record.email, record.role, etc.
  });
}
```

---

## 9. Best Practices (Official Recommendations)

**Source:** https://playwright.dev/docs/best-practices

**Testing philosophy:**
- Test user-visible behavior, not implementation details
- Isolate tests: each test gets own data, cookies, storage
- Mock external dependencies (don't test third-party sites)
- Prefer user-facing attributes (role, label, text) over CSS/XPath

**Locator best practices:**
- Use built-in locators with auto-wait/retry
- Use `codegen` to generate resilient locators
- Chaining and filtering for precise targeting
- Avoid targeting by CSS classes or ids that may change

**Assertions:**
- Use web-first assertions: `toBeVisible()`, `toHaveText()`, `toHaveURL()`
- These auto-wait for the condition to be met
- Avoid `isVisible()` (doesn't auto-wait, you handle timing)
- Soft assertions: `expect.soft()` for non-blocking checks

**CI/CD:**
- Run tests on every commit/PR
- Use Linux containers for cost efficiency
- Implement sharding for parallel execution
- Keep Playwright version updated

**Debugging:**
- VS Code extension for local debugging
- `--debug` flag for headed browser with inspector
- Trace viewer for CI failure investigation (preferred over screenshots/videos)
