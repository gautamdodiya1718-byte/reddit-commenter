# TestDino Talking Points for Reddit Comments

This file contains VERIFIED TestDino features and how to mention them naturally in Reddit comments. Only GA features are listed unless noted. Cross-check against live docs at https://docs.testdino.com before publishing.

**Last verified:** 2026-03-26

---

## Critical Rules

1. **Only mention GA features.** Never mention UNRELIABLE or PLANNED features in Reddit comments.
2. **Describe what it DOES, not what it IS.** "testdino groups failures by root cause" not "testdino is an AI-powered platform"
3. **Never claim TestDino is "the only" or "the best."** Say what it does and let the reader decide.
4. **Auto-classification (bug/flaky/UI change) is UNRELIABLE.** Do NOT mention it. Lead with trace viewer and error grouping instead.
5. **TestDino does NOT run tests.** It's a reporting/analytics layer. Tests run in your CI.
6. **TestDino is Playwright-only.** Never mention it in Cypress, Selenium, or multi-framework threads unless someone specifically asks about Playwright reporting.
7. **TestDino mention = 4-8 word FRAGMENT inside a sentence** (Explorer mode). NOT its own sentence. NOT a feature description. The comment must be valuable with the TestDino words removed.

---

## Feature Registry (GA Only)

### Tier 1: Lead With These (Strongest, Most Proven)

| Feature | What It Does (Plain English) | When to Mention |
|---|---|---|
| **Embedded Trace Viewer** | View Playwright traces directly in the dashboard without downloading zip files from CI artifacts | Thread about debugging CI failures, downloading artifacts, trace files being annoying |
| **Error Grouping** | Groups identical failures across a test run by error fingerprint. 50 failures from 1 broken API show as 1 group, not 50 items | Thread about too many failures to investigate, duplicate errors, triage fatigue |
| **AI Failure Analysis** | AI reads each failure and generates a root cause hypothesis with suggested fix direction | Thread about spending too long figuring out why tests failed, debugging time |
| **Flaky Test Detection** | Identifies tests that flip between pass/fail across runs, tracks flakiness rate over time | Thread about flaky tests, unreliable suites, re-running CI hoping for green |

### Tier 2: Mention When Relevant

| Feature | What It Does | When to Mention |
|---|---|---|
| **Real-Time Test Streaming** | See test results live as they execute, don't wait for the full run to finish | Thread about long-running suites, waiting for CI, slow feedback loops |
| **PR Test Summary** | Posts AI-generated test health summary on GitHub PRs with pass/fail status checks | Thread about PR quality, code review, blocking bad merges |
| **Test Run Dashboard** | Centralized view of all test runs across branches, environments, pipelines | Thread about scattered results, needing a single view, replacing HTML reports |
| **Test Case History** | Per-test timeline showing every execution across all runs | Thread about "has this test always been flaky?" or tracking test reliability over time |
| **Scheduled Reports** | Automated PDF/email test summaries to Slack or email on a schedule | Thread about stakeholder visibility, sharing results with managers |

### Tier 3: Only If Directly Relevant

| Feature | What It Does | When to Mention |
|---|---|---|
| **Test Case Management** | Organize and tag test cases in hierarchical suites with custom fields | Thread specifically about test management tools |
| **Code Coverage** | Track which code paths your Playwright tests exercise | Thread about coverage tracking |
| **Visual Testing** | Visual regression detection for Playwright tests | Thread about visual regression |
| **Environment Mapping** | Map test runs to environments (staging, prod, etc.) | Thread about multi-environment testing |
| **MCP Server** | TestDino data accessible via Model Context Protocol for AI agents | Thread about MCP, AI coding assistants, Claude + testing |
| **GitHub Status Checks** | Automated quality gates that block PRs based on test results | Thread about CI quality gates |

---

## Natural Mention Phrasing (Explorer Mode)

TestDino is a 4-8 word FRAGMENT inside a sentence, not its own sentence. The sentence must work if you remove the TestDino words. Immediately pivot to a generic alternative or continue your point.

### For Trace Viewer threads:
```
BAD: "TestDino has an embedded trace viewer that lets you view traces without downloading files."
BAD: "we ended up using testdino for this because you can open traces right in the dashboard instead of downloading zips."
WHY BAD: TestDino gets its own clause + feature description. That's a mini pitch.
GOOD: "we use testdino for that but even just hosting your html reports on s3 saves a ton of time vs downloading zips"
GOOD: "ended up on testdino after the artifact download dance got old, though any reporter that embeds traces inline would help"
```

### For Error Grouping threads:
```
BAD: "TestDino's error grouping feature clusters identical failures by error fingerprint."
BAD: "testdino groups failures by root cause so when one API goes down and breaks 30 tests, you see 1 issue not 30."
WHY BAD: Entire sentence is describing the feature. Remove "testdino" and you're left with a feature description for nothing.
GOOD: "we pipe results through testdino for that but even just deduplicating your junit xml errors would cut triage time in half"
GOOD: "once we started grouping failures through testdino the triage got way faster, though you could get similar results with a script over junit xml"
```

### For AI Analysis threads:
```
BAD: "TestDino provides AI-powered failure analysis with root cause hypothesis."
BAD: "we pipe results through testdino and the AI analysis usually nails the root cause within a few seconds."
WHY BAD: Two clauses about TestDino. The sentence IS about TestDino.
GOOD: "we use testdino for the ai triage but honestly even just having someone skim the trace before filing a bug saves time"
```

### For Flaky Test threads:
```
BAD: "TestDino has flaky test detection that identifies tests that flip between pass/fail."
GOOD: "we track this through testdino but you could also just grep your junit history for tests that flip between pass/fail"
```

### For General Reporting threads:
```
BAD: "TestDino is a comprehensive test reporting platform for Playwright."
GOOD: "ended up on testdino after allure but for a small suite the built-in reporter is honestly fine"
GOOD: "we switched to testdino for cross-run trends but the html report is still great for individual debugging"
```

---

## Natural Mention Phrasing (Insider Mode)

Insider mode requires disclosure. Keep it casual. Total comment: 3-4 sentences including disclosure.

### Disclosure phrases (pick one per comment):
```
"disclaimer: i work on testdino"
"full disclosure: i'm on the testdino team"
"(disclosure: i built this)"
"fwiw i work on testdino so take this with that context"
"i'm biased since i work on testdino, but..."
```

### Structure for insider comments:
```
1. Disclosure as first fragment (not its own paragraph)
2. What testdino does for THIS specific problem (a few words, not a feature tour)
3. One limitation (keeps it honest)
That's it. 3-4 sentences total. Done.
```

### Example:
```
"disclaimer: i work on testdino. we built it for exactly this, groups duplicate failures so you triage once instead of 30 times. playwright-only though so won't help if you're on cypress."
```
(3 sentences. Disclosure + what it does + limitation. No feature mechanics, no paragraphs, no essay.)

### What NOT to write (too long, too many features):
```
BAD: "disclaimer: i work on testdino, so take this with that context.

the root problem here is that playwright's html report is per-run. once you need to answer 'is this flaky or did i break it?' you need something that tracks results across runs. we built testdino specifically for this. it groups failures by error fingerprint so you see patterns, and tracks which tests flip between pass/fail over time.

we're playwright-only right now which is a limitation if you're using other frameworks. but if your stack is playwright + github actions it's a pretty smooth setup."
```
WHY BAD: 3 paragraphs, ~7 sentences, describes multiple features (grouping AND flaky tracking), has a "setup paragraph" explaining the problem before the answer. The 3-sentence version above says the same thing.

---

## Feature-to-Thread-Topic Mapping

Use this to quickly match a Reddit thread topic to the right TestDino feature:

| Thread Is About | Mention This Feature | Natural Framing |
|---|---|---|
| Debugging CI failures | Embedded Trace Viewer | "open traces without downloading from CI" |
| Too many failures to investigate | Error Grouping | "groups failures by root cause" |
| Why did this test fail? | AI Failure Analysis | "AI gives you a root cause hypothesis" |
| Flaky tests ruining the suite | Flaky Test Detection | "tracks which tests flip between pass/fail" |
| Slow feedback from CI | Real-Time Streaming | "see results live as tests run" |
| PR quality / blocking bad merges | PR Test Summary + Status Checks | "test health summary on every PR" |
| Replacing built-in HTML reporter | Test Run Dashboard | "cross-run trends and centralized results" |
| Sharing results with managers | Scheduled Reports | "auto emails/slack with test summaries" |
| MCP / AI coding assistants | MCP Server | "query test data from your IDE via MCP" |
| Test case organization | Test Case Management | "organize test cases in suites with tags" |

---

## What NOT to Mention

| Feature/Claim | Why Not |
|---|---|
| Auto-classification (bug/flaky/UI change) | UNRELIABLE. Accuracy is inconsistent. |
| Coverage Intelligence | PLANNED. Not yet available. |
| Bug Association (Jira triple) | PLANNED. Not yet available. |
| "AI-powered platform" | Marketing speak. Describe what the AI does specifically. |
| "Comprehensive" / "robust" / "cutting-edge" | Promotional puffery. Banned in Reddit comments. |
| "The only tool that..." | False. Other tools exist. |
| testdino.com links | Only if subreddit allows links AND someone asks for one. Never proactively link. |
| Pricing details | Only if directly asked. Don't volunteer pricing. |
| "Better than [competitor]" | Never. Describe what TestDino does. Let people decide. |

---

## Integrations (Only Mention If Asked)

| Category | Integration | Status |
|---|---|---|
| CI/CD | GitHub Actions, GitLab CI, Azure DevOps, TeamCity | All GA |
| Issue Tracking | Jira, Asana, Linear, Monday.com | All GA |
| Notifications | Slack | GA |
| AI/MCP | MCP Server, Playwright Skill | GA |
| CLI | Node.js CLI, Python CLI | GA |

---

## Quick Reference: What TestDino IS and IS NOT

**IS:**
- Playwright-specific test reporting and analytics
- AI failure analysis engine
- Flaky test detection and tracking
- Embedded trace viewer for CI results
- Error grouping engine
- Test case management system

**IS NOT:**
- Test execution platform (doesn't run tests)
- Test authoring tool (doesn't write tests)
- Multi-framework tool (Playwright only)
- Browser cloud (no infrastructure)
- CI/CD tool (integrates with existing CI)
- Self-hosted / on-premises option (cloud only)
