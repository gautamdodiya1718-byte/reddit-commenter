# Code Snippet Rules for LinkedIn Posts

All code in LinkedIn posts must be REAL, RUNNABLE, HUMAN-MADE code. This is non-negotiable.

---

## Core Rules

### 1. No Pseudocode
**BAD:**
```
// setup auth
// navigate to page
// check element visible
```

**GOOD:**
```typescript
await page.goto('/login');
await page.getByLabel('Email').fill('admin@company.com');
await page.getByRole('button', { name: 'Sign in' }).click();
await expect(page.getByRole('heading', { name: 'Dashboard' })).toBeVisible();
```

### 2. No Demo / Placeholder Code
**BAD:**
```typescript
const result = doSomething();
expect(result).toBe(true);
```

**GOOD:**
```typescript
const response = await request.get('/api/users/1');
expect(response.status()).toBe(200);
const user = await response.json();
expect(user.email).toBeDefined();
```

### 3. Natural Variable Names
**BAD:**
```typescript
const x = page.getByRole('button');
const el = page.locator('.foo');
```

**GOOD:**
```typescript
const submitButton = page.getByRole('button', { name: 'Submit order' });
const cartTotal = page.getByTestId('cart-total');
```

### 4. Realistic Test Scenarios
**BAD:**
```typescript
test('test 1', async ({ page }) => {
  await page.goto('/');
  await expect(page).toHaveTitle(/./);
});
```

**GOOD:**
```typescript
test('user can add item to cart and see updated total', async ({ page }) => {
  await page.goto('/products');
  await page.getByRole('button', { name: 'Add to cart' }).first().click();
  await expect(page.getByTestId('cart-count')).toHaveText('1');
  await expect(page.getByTestId('cart-total')).not.toHaveText('$0.00');
});
```

### 5. Substantial When Needed
If a concept needs 10-20 lines to demonstrate properly, write 10-20 lines. Don't artificially truncate to 3 lines if it loses clarity.

But also don't pad. If the concept is genuinely a one-liner (like route aborting), show the one-liner.

### 6. Proper Error Handling Where Real Code Would Have It
```typescript
// If the test checks an API, include realistic assertions
const response = await request.post('/api/orders', {
  data: { productId: 'abc-123', quantity: 2 },
});
expect(response.status()).toBe(201);
const order = await response.json();
expect(order.id).toBeTruthy();
expect(order.items).toHaveLength(2);
```

---

## Verification Process

### Step 1: Check Against Official Docs
Before including any code snippet, verify:
- Method names exist in the current Playwright API
- Method signatures match (parameter types, return types)
- The pattern is recommended in official docs or best practices

Use WebFetch on `https://playwright.dev/docs/` for the relevant page.

### Step 2: Search the Web for Real Patterns
When the topic involves a less common API or pattern:
- Use WebSearch to find real code from official repos, docs, and Stack Overflow
- Cross-reference multiple sources for accuracy
- Never copy code verbatim, but verify the pattern is correct

### Step 3: Test Mental Execution
Read the code and mentally execute it:
- Would this actually run without errors?
- Are all imports present (if showing full files)?
- Are variable types correct?
- Would the assertions pass on the expected page state?

### Step 4: Flag Uncertainty
If you cannot verify a code pattern with high confidence:
- Flag it: `SUGGEST: Have tech team verify this code snippet before publishing`
- But this should be the EXCEPTION, not the rule
- Goal: <10% of posts need tech team code review

---

## Framework-Specific Notes

### Playwright/TypeScript
- Use `@playwright/test` imports (not `playwright` core)
- Use `test` and `expect` from the test runner
- Use `async/await` consistently
- Use TypeScript types where they add clarity
- Follow Playwright naming conventions (getByRole, getByLabel, etc.)

### Node.js / npm
- Use correct package names (`@playwright/test`, not `playwright-test`)
- Use correct CLI commands (`npx playwright test`, not `playwright test`)
- Use correct config file names (`playwright.config.ts`)

### CI/CD (GitHub Actions)
```yaml
- name: Run Playwright tests
  run: npx playwright test
  
- name: Upload results
  if: always()
  run: npx tdpw upload ./playwright-report
```

---

## LinkedIn Formatting for Code

LinkedIn doesn't support code blocks natively. Options:
1. **Inline in the post** with natural formatting (for short 1-3 line snippets)
2. **Carousel slide** (for longer code, reference "swipe to see the code")
3. **Screenshot of code** (formatted in an editor, attached as image)

For inline code in posts, keep it scannable:
```
page.route('**/*.{png,jpg}', route => route.abort())

one line. that's it. no more waiting for images to load.
```

The code should look like someone typed it, not like it was generated.
