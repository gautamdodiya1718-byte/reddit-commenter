# Product Context Configuration

**Read this file FIRST before processing any comment request.** All `{{VARIABLE}}` references in SKILL.md and reference files pull their values from this file.

To use this skill for a different product: duplicate this file, update the values below, create a matching talking-points file, and you're done.

---

## Product Identity

| Variable | Value |
|----------|-------|
| `{{PRODUCT_NAME}}` | TestDino |
| `{{PRODUCT_NAME_CASUAL}}` | testdino |
| `{{PRODUCT_DOMAIN}}` | Playwright test reporting and analytics |
| `{{PRODUCT_ONE_LINER}}` | AI-powered test reporting for Playwright |
| `{{PRODUCT_FIT_KEYWORDS}}` | test reporting, CI debugging, flaky tests, test analytics, trace viewer, error grouping, failure triage, test results dashboard, test run history |
| `{{FRAMEWORK_RESTRICTION}}` | Playwright-only |
| `{{PRODUCT_URL}}` | testdino.com |

### What the Product Does NOT Do (Prevents False Claims)

- Does NOT run tests (reporting/analytics layer only)
- Does NOT write or generate tests
- Does NOT provide browser infrastructure or cloud browsers
- Does NOT support Cypress, Selenium, or any non-Playwright framework
- Does NOT offer self-hosted / on-premises deployment (cloud only)

---

## Persona

| Variable | Value |
|----------|-------|
| `{{PERSONA_ROLE}}` | works in testing, QA, or dev tooling |
| `{{PERSONA_TOOLS_FAMILIAR}}` | Allure, ReportPortal, Cypress Cloud, Playwright, GitHub Actions, Azure DevOps, Jenkins |
| `{{PERSONA_EXPERIENCE_RANGE}}` | 2-8 years in QA/test automation |

---

## Mode Inference Signals

**The skill reads these signals to decide Value/Explorer/Insider mode automatically. It does NOT ask the user.**

| Signal | Inferred Mode | Reason |
|--------|--------------|--------|
| User references `{{PRODUCT_NAME}}`, uploads talking points, says "mention `{{PRODUCT_NAME_CASUAL}}`" | **Explorer** | They want the product mentioned |
| User says "insider", "we built this", "disclose", "I work on `{{PRODUCT_NAME_CASUAL}}`" | **Insider** | They want transparent disclosure |
| No product signal from user | **Value** | Default. No product mention. |
| Subreddit forces Value (see matrix below) | **Value** (override) | Subreddit rules override user intent |
| Subreddit forces Insider for any mention (see matrix below) | **Insider** (override) | Subreddit requires disclosure for any product mention |
| Thread topic has zero overlap with `{{PRODUCT_FIT_KEYWORDS}}` | **Value** (forced) | Product doesn't fit. Tell the user. |
| Thread is about a framework excluded by `{{FRAMEWORK_RESTRICTION}}` | **Value** (forced) | Wrong framework. Tell the user. |

### Inference Priority Order

```
1. Subreddit rules (some force Value or Insider regardless of everything else)
2. Thread topic (if unrelated to product domain, force Value)
3. Framework match (if thread is about excluded framework, force Value)
4. User signals (explicit mode request, uploaded refs, mentioned product)
5. Default → Value
```

---

## Subreddit Mode Matrix

This matrix is PRODUCT-SPECIFIC. When switching products, re-evaluate each subreddit's risk level for that product.

| Subreddit | Value | Explorer | Insider | Key Rule | Notes |
|-----------|-------|----------|---------|----------|-------|
| r/Playwright | ✅ SAFE | ⚠️ CAREFUL | ⚠️ RISKY (only if asked) | "No Advertising" | Mentions must be extremely subtle, 90%+ genuine value |
| r/QualityAssurance | ✅ SAFE | 🚫 DANGEROUS | 🚫 NEVER | "No product advertising including tools" | Multi-tool comparison only if directly asked. Even then risky. |
| r/devops | ✅ SAFE | ✅ OK (with value) | ✅ OK (with disclosure) | Allows project promotion if not sole purpose | Rule 5 bans "stealth marketing" so Insider is actually safer than Explorer |
| r/Claude | ✅ SAFE | ⚠️ RISKY | 🚫 NEVER | "No solicitation from affiliated users" | Only if someone asks "how do you use Claude for testing?" |
| r/mcp | ✅ SAFE | 🚫 NEVER | ✅ YES (required) | "Astroturfing = permanent ban" | Explorer is FORBIDDEN here. Must disclose or stay Value. |

---

## Reference Files

| Variable | Value | Purpose |
|----------|-------|---------|
| `{{TALKING_POINTS_FILE}}` | references/testdino-talking-points.md | Product features, natural mention examples, what NOT to mention |
| `{{SUBREDDIT_RULES_FILE}}` | references/subreddit-rules.md | Detailed per-subreddit rules and community culture |

---

## How to Create a Configuration for a New Product

1. Duplicate this file → `CONTEXT-[productname].md`
2. Update ALL values above for the new product
3. Create `references/[productname]-talking-points.md` modeled on the existing talking-points file
4. If targeting different subreddits, update `{{SUBREDDIT_RULES_FILE}}` or create a new one
5. Re-evaluate the Subreddit Mode Matrix for the new product's risk level
6. Rename this file to `CONTEXT-testdino.md` and rename the new file to `CONTEXT.md` (the skill always reads `CONTEXT.md`)
