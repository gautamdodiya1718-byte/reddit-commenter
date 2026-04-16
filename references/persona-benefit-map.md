# Persona Benefit Mapping: FEEL, Not State

Self-contained persona targeting logic. Auto-detects which personas to address from the post content.

---

## AUTO-DETECTION: Which Personas to Address

Don't ask the user "who is this for?" Infer from the content:

```
CONTENT SIGNAL                              → PRIMARY PERSONA
────────────────────────────────────────────────────────────
CI failures, debugging, PR feedback loops   → Developer
Triage workflows, reporting, flaky tracking → QA Engineer
Framework architecture, scaling 500+ tests  → SDET
Pipeline velocity, sprint delivery, risk    → CTO
Scattered results, handoff friction         → Team
Release confidence, deployment frequency    → Business (minimal)
```

Pick 1-2 personas per post. Never try to address all 6. The post's scenario naturally resonates with the right personas.

**Priority order:** Developer > QA > SDET > CTO > Team > Business (business gets LEAST focus)

---

## RULE: FEEL, NOT STATE

**NEVER write:** "Benefits for developers: X" or "This helps QA teams by..."
**INSTEAD:** Write scenarios that make the persona FEEL the benefit without being told.

The reader finishes the post and thinks "this would change how I work" without ever being told "this benefits you."

---

## DEVELOPER (Primary Audience)

**Make them feel:** "This would save me time and stop the interruptions"

**Scenario patterns that resonate:**
- Getting pinged at 3pm because a test they never wrote is failing on their PR
- 20 minutes downloading trace zips to debug a 5-second failure
- Test passes locally, fails in CI, zero context about what's different
- Context-switching from feature work to investigate an unrelated flaky test
- Waiting 35 minutes for the full suite to re-run because 3 tests failed
- Slack message: "tests are red" with no detail about which, why, or whose fault

**Writing technique:** Put the developer IN the scenario with "you" language. Describe the interruption, the context-switch cost, the time sink. The solution naturally shows how the pain goes away.

**Example (GOOD):**
> The CI fails on your PR. You click through the logs. 47 failures. You check the first three. Same error. A broken API endpoint that has nothing to do with your change.

**Example (BAD):**
> Developers benefit from error grouping because it reduces investigation time.

---

## QA ENGINEER

**Make them feel:** "I'd stop being the bottleneck"

**Scenario patterns:**
- Being the person who explains to devs what failed, why, and where the trace is
- Manually building test reports every Monday
- Tracking flaky tests in a spreadsheet
- Half the day triaging failures that are duplicates
- Getting blamed when tests fail even though the code is the problem

**Writing technique:** Show the workflow friction. QA feels the pain of being the communication bridge.

**Example (GOOD):**
> Pipeline fails. Dev asks: "What happened?" QA downloads the trace, reads the error, writes a summary, posts it in Slack. Repeat for every failure. Every day.

---

## SDET

**Make them feel:** "My framework would scale better"

**Scenario patterns:**
- Framework works for 50 tests, breaks at 500
- Page objects across 3 environments with different configs
- 8 engineers all writing tests differently
- Fixtures vs hooks vs utility functions debate
- Sharding across 4 machines and merging reports
- Test that only fails in parallel, never in isolation

**Writing technique:** Talk about architectural decisions and scaling. SDETs think in systems, not individual tests.

---

## CTO

**Make them feel:** "My team would ship faster with less risk"

**Scenario patterns:**
- Sprint velocity dropping because pipeline is unreliable
- Engineers spending 20% of their week on test failures instead of features
- Can't answer "are we safe to release?" with confidence
- Test infra costs growing but reliability staying flat

**Writing technique:** Frame in terms of velocity, risk, and throughput.

---

## TEAM

**Make them feel:** "We'd collaborate better"

**Scenario patterns:**
- Dev and QA pointing fingers when tests fail
- Nobody knows which tests are flaky vs genuinely broken
- Results scattered across CI logs, Slack, and email
- The person who knows why a test fails is on vacation

---

## BUSINESS (Minimal Focus)

**Make them feel:** "Releases would be safer"

Use sparingly. Business benefit is the implicit consequence of solving developer/QA/SDET problems.

**Example (GOOD, brief):** "Friday deployments stopped being scary when the team could actually trust the results."

**Example (BAD):** "TestDino helps businesses reduce time-to-market by improving test reliability."

---

## HOW TO APPLY

1. Auto-detect 1-2 personas from the content signal table above
2. Put the reader in the scenario using "you" language
3. Show the pain first (80%), then the resolution (20%)
4. Never label the persona in the post
5. The reader self-identifies. A developer reads about CI triage and FEELS the time savings.
6. Business benefits are always implied, never stated.
