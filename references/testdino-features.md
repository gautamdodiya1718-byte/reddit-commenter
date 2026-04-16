# TestDino Verified Feature Registry

Adapted from reddit-commenter/testdino-talking-points.md + verified against live docs at https://docs.testdino.com/

**CRITICAL**: This file is a STARTING POINT only. The skill MUST WebFetch live docs at https://docs.testdino.com/ EVERY TIME it generates a TestDino-related post. This file gets updated when discrepancies are found.

**Last verified:** 2026-04-15

---

## Critical Rules

1. **Only mention GA features.** Never mention UNRELIABLE or PLANNED features.
2. **Describe what it DOES, not what it IS.** "testdino groups failures by root cause" not "testdino is an AI-powered platform"
3. **Never claim TestDino is "the only" or "the best."** Describe what it does. Let the reader decide.
4. **Auto-classification (bug/flaky/UI change) is UNRELIABLE.** Do NOT mention it.
5. **TestDino does NOT run tests.** It's a reporting/analytics layer. Tests run in your CI.
6. **TestDino is Playwright-only.** Never mention it in contexts about other frameworks unless someone asks specifically.
7. **ALWAYS verify against live docs** before including any feature claim in a post. Use WebFetch on https://docs.testdino.com/ every time.
8. **Frame features as customer-driven.** "an sdet running 400+ tests kept hitting..." not "we added..."

---

## Feature Registry (GA Only)

### Tier 1: Lead With These (Strongest, Most Proven)

| Feature | What It Does (Plain English) | Customer-Driven Framing |
|---|---|---|
| **Embedded Trace Viewer** | View Playwright traces directly in the dashboard without downloading zip files from CI artifacts | "an sdet was spending 2 minutes per failure downloading and opening trace zips from ci artifacts. multiply that by 15 failures per run." |
| **Error Grouping** | Groups identical failures across a test run by error fingerprint. 50 failures from 1 broken API show as 1 group, not 50 items | "50 tests failed. all from the same broken api endpoint. but the report shows 50 separate items. the team kept investigating duplicates." |
| **AI Failure Analysis** | AI reads each failure and generates a root cause hypothesis with suggested fix direction | "a qa lead was spending 30 minutes per run just reading stack traces to figure out what went wrong. they needed the first hypothesis faster." |
| **Flaky Test Detection** | Identifies tests that flip between pass/fail across runs, tracks flakiness rate over time, categorized by root cause (timing, environment, network, assertion) | "the team kept re-running the pipeline hoping for green. nobody knew which tests were actually flaky vs genuinely broken." |

### Tier 2: Mention When Relevant

| Feature | What It Does | Customer-Driven Framing |
|---|---|---|
| **Real-Time Test Streaming** | See test results live as they execute, don't wait for the full run to finish | "engineers were waiting 20 minutes for the full suite to finish before seeing which tests failed first." |
| **PR Test Summary** | Posts AI-generated test health summary on GitHub PRs with pass/fail status checks | "code reviewers had no idea if the tests passed without leaving github and checking a separate dashboard." |
| **Test Run Dashboard** | Centralized view of all test runs across branches, environments, pipelines with role-based views (dev/sdet/manager) | "results were scattered across ci logs, html reports, and slack messages. nobody had the full picture." |
| **Test Case History** | Per-test timeline showing every execution across all runs with up to 10 previous executions | "a test started failing on tuesday but nobody noticed until friday. no history to trace back when it started." |
| **Scheduled Reports** | Automated PDF summaries delivered on daily, weekly, or monthly cadence | "the engineering manager kept asking for test health updates. the qa lead was manually creating reports every monday." |
| **Failed Test Rerunning** | Re-run only what failed to cut pipeline time. Intelligent grouping by branch and commit. | "the full suite took 35 minutes. 3 tests failed. re-running everything took another 35 minutes just to verify 3 tests." |

### Tier 3: Only If Directly Relevant

| Feature | What It Does | When to Mention |
|---|---|---|
| **Test Case Management** | Organize test cases, suites, and ownership linked to real runs with bulk operations | Thread specifically about test management |
| **Visual Testing** | Visual regression detection for Playwright tests with side-by-side diff comparison (baseline vs actual) | Thread about visual regression |
| **Environment Mapping** | Map Git branches to environments (Dev, Staging, Production) with exact match and regex patterns | Thread about multi-environment testing |
| **MCP Server** | TestDino data accessible via Model Context Protocol for AI agents to query test runs, logs, traces | Thread about MCP, AI coding assistants |
| **GitHub Status Checks** | Quality gates that block PRs based on configurable pass rate thresholds (0-100%), mandatory test tags, flaky test handling modes | Thread about CI quality gates |
| **Component Testing** | Supports Playwright component testing (Beta) for React, Vue, Svelte | Thread specifically about component testing |

---

## Integration Registry (GA)

| Category | Integration | Status |
|---|---|---|
| CI/CD | GitHub Actions, GitLab CI, Azure DevOps, TeamCity | All GA |
| Issue Tracking | Jira, Asana, Linear, Monday.com | All GA |
| Notifications | Slack (App + Webhook) | GA |
| AI/MCP | MCP Server | GA |
| CLI | Node.js CLI (tdpw), Python CLI | GA |

---

## What NOT to Mention

| Feature/Claim | Why Not |
|---|---|
| Auto-classification (bug/flaky/UI change) | UNRELIABLE. Accuracy is inconsistent. |
| Coverage Intelligence | PLANNED. Not yet available. |
| Bug Association (Jira triple) | PLANNED. Not yet available. |
| "AI-powered platform" | Marketing speak. Describe what the AI does specifically. |
| "Comprehensive" / "robust" / "cutting-edge" | Promotional puffery. Banned. |
| "The only tool that..." | False. Other tools exist. |
| testdino.com links in posts | Only if someone directly asks. Never proactively link. |
| Pricing details | Only if directly asked. Don't volunteer. |
| "Better than [competitor]" | Never compare. Describe what TestDino does. |

---

## What TestDino IS and IS NOT

**IS:**
- Playwright-specific test reporting and analytics
- AI failure analysis engine (generates root cause hypothesis)
- Flaky test detection and tracking
- Embedded trace viewer for CI results
- Error grouping engine
- Test case management system
- Real-time test streaming dashboard

**IS NOT:**
- Test execution platform (doesn't run tests)
- Test authoring tool (doesn't write tests)
- Multi-framework tool (Playwright only)
- Browser cloud (no infrastructure)
- CI/CD tool (integrates with existing CI)
- Self-hosted / on-premises option (cloud only)

---

## CLI Quick Reference (for code snippets)

```bash
# Install
npm install tdpw

# Upload results
npx tdpw upload ./playwright-report

# Upload with visual testing images
npx tdpw upload ./playwright-report --upload-images

# Upload with full artifacts
npx tdpw upload ./playwright-report --upload-html

# Cache test metadata for smart reruns
npx tdpw cache

# Get previously failed tests for selective rerun
npx tdpw last-failed
```

**Environment Variables:**
- `TESTDINO_TOKEN` - API authentication (required)
- `TESTDINO_TARGET_ENV` - Default environment tag
- `TESTDINO_RUN_TAGS` - Default comma-separated run tags

**Setup Requirements:**
- Playwright test framework configured
- Git initialized (for branch/commit extraction)
- JSON reporter required (mandatory)
- HTML reporter listed BEFORE JSON reporter
- Use `if: always()` in CI for uploads on test failures
