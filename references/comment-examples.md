# Comment Examples

Real quotes from 322 pages of Reddit data (r/Playwright, r/QualityAssurance, r/devops, r/Claude, r/mcp) plus calibrated examples for each mode. Every "Real Quote" section is copied verbatim from actual Reddit comments.

---

## Part 1: Real Reddit Comments (Verbatim from PDF Data)

These are ACTUAL comments real people wrote. Study the patterns, the messiness, the personality. This is the standard to match.

---

### Real Quote 1: The Experience Sharer (most common pattern, ~35% of comments)

**Source:** r/Playwright, tool recommendation thread
```
We went through the same evolution. Started with CI artifacts (download zip, open locally), then moved to uploading the HTML report to a self-hosted dashboard.
The thing nobody mentions is that Playwright's built-in reporter is great for individual test debugging but terrible for trends. You can't answer "is this test flaky this week?" or "did this failure happen before?" without something that persists results across runs.
What ended up working: jUnit XML into the CI platform for the pass/fail overview, and the full trace/screenshot artifacts uploaded to a dedicated test results dashboard. Slack notification on failures with a direct link. The key is making sure the person who sees the failure can get to the trace in one click -- anything more than that and people just re-run and hope.
```
**Patterns observed:**
- Opens with "We went through the same evolution" (team experience, relatable)
- "The thing nobody mentions is" (opinionated, positions them as knowing something others don't)
- Specific technical stack (jUnit XML, Slack, CI artifacts)
- Ends with an insight, not a sign-off ("people just re-run and hope")
- Three paragraphs: short intro, medium critique, long solution. UNEVEN.
- One em dash (rare for real comments but this person used one; shows they're not banned outright, just AI overuses them)

---

### Real Quote 2: The Frustrated Venter (emotional, lowercase, ~8% of comments)

**Source:** r/QualityAssurance, test maintenance thread
```
every feature release means 15 to 20 tests need updates. every ui redesign is a disaster. even with good locator strategies and test ids everywhere, tests still break constantly. dom structure changes, someone refactors a component, animations get added, whatever.

tried being really smart about it. used the best practices, got devs to add data-testid attributes, used text based selectors when possible. still doesn't matter. maintenance is endless.

honestly starting to question my career choice here. got into qa because i wanted to improve product quality and find interesting bugs. instead i'm just a test maintenance engineer updating selectors all day.
```
**Patterns observed:**
- All lowercase throughout (consistent voice)
- Specific numbers ("15 to 20 tests")
- Fragments ("maintenance is endless.", "still doesn't matter.")
- Emotional vulnerability ("questioning my career choice")
- No solution offered. Just pain. (Real people don't always have answers)
- "whatever" at end of list (casual dismissal)
- Short punchy sentences mixed with longer ones

---

### Real Quote 3: The Blunt Corrector (~16% of comments)

**Source:** r/Playwright, selector strategy thread
```
A playwright alternative with less maintenance is just playwright with better test writing discipline. Sorry but most playwright maintenance problems are self-inflicted through bad selector strategy and tight coupling to implementation details. The tool is not the problem. The problem is teams that write tests against things that were never stable and then blame the framework when those things change.
```
**Patterns observed:**
- Opens with a direct contradiction of the premise
- "Sorry but" is the ONLY softener before the blunt truth
- Single paragraph wall of text
- Strong opinion with zero hedging
- Ends with a mic-drop statement ("blame the framework when those things change")
- No bullet points, no formatting, just prose

---

### Real Quote 4: The Casual Swearer (~7% of comments)

**Source:** r/Playwright, Claude + MCP thread
```
holy shite, i just bought claude and its amazing together with the claude code and mcp but holy fk the usage is terrible for the pro plan. just worked not even 2hours and got limit to go again in 3hours. Imagine if my work actually depended on it.. I would be fked.. I mean it probablly did though the work i would do in more than 4hours in 20mins but still. Is there any unlimited version?
```
**Patterns observed:**
- Self-censored profanity ("fk", "fked") 
- Typos ("probablly")
- Double periods for trailing off ("..")
- "I mean" as a filler/softener
- "its" instead of "it's"
- No paragraph breaks at all (wall of text)
- Ends with a question
- Mixed capitalization (lowercase "i" but capitalized "Imagine")
- Specific numbers ("2hours", "3hours", "4hours", "20mins")

---

### Real Quote 5: The Empathetic Helper (~6% open with empathy)

**Source:** r/QualityAssurance, test maintenance frustration
```
dude, I feel this so hard. switched for the same reasons and yeah, the maintenance tax is brutal. I swear I was just a glorified CSS selector janitor for like a year.

what helped me a bit—and this sounds obvious but it took me forever to internalize—was accepting that some breakage is inevitable and trying to make the feedback loop as fast as possible. like, if a PR breaks 20 tests, I need to know which ones and why in under a minute, not after a 30-minute run.

also, maybe controversial, but I stopped chasing perfect, unbreakable selectors. sometimes a simple role+name or text selectors that breaks is faster to update than debugging a super-fragile but "robust" selectors strategy.
```
**Patterns observed:**
- "dude, I feel this so hard" (genuine empathy, not formulaic)
- "glorified CSS selector janitor" (creative self-deprecation)
- "like" used as casual filler ("like, if a PR breaks 20 tests")
- "maybe controversial, but" (flags opinion as potentially disagreeable)
- Contractions everywhere ("doesn't", "I'm", "wasn't")
- Mix of lowercase and standard capitalization
- "supper" for "super" (actual typo left uncorrected)
- Three paragraphs: empathy, advice, opinion. Uneven lengths.

---

### Real Quote 6: The One-Word/One-Line Answer (~20% of comments)

**Source:** r/QualityAssurance, "what reporter do you use?"
```
Reportportal
```

**Source:** r/Playwright, debugging thread
```
You're almost certainly using the wrong locators if they're that fragile. Use the playwright suggested ones.
```

**Source:** r/Playwright, agreement
```
Underrated comment.
```

**Patterns observed:**
- No explanation. No justification. Just the answer.
- Single word answers are REAL and COMMON.
- "You're almost certainly" is a confident statement without being rude
- Zero formatting, zero structure

---

### Real Quote 7: The Structural Deep Dive (~17% of longer answers)

**Source:** r/QualityAssurance, test approach discussion
```
Some teams use the Jenkins plugin for Allure, but mostly we run the tests all the time so value of history is just based on what was included in a TSR for a release rather than needing to see it. Comparing this run to last run is usually enough.

We have been doing a scrape of the result data and pushing it to a PostgresDB for further analysis and reporting. Doesn't capture step level, just test level. It's hard to find a solution that applies for dashboarding off the top of the data though. Either they are way to complicated/boring to keep refreshed or the company has segregation of duties to keep data isolated (don't mix test data with prod) so no using app support tools for dashboards. So that's got a model but is in progress for a better solution.
```
**Patterns observed:**
- "way to complicated" (should be "too" -- real typo left in)
- Long second paragraph (wall of text, should be broken up but wasn't)
- Mentions specific tools (Jenkins, Allure, PostgresDB)
- Acknowledges limitations ("in progress for a better solution")
- Parenthetical aside ("don't mix test data with prod")
- No opener, no closer. Starts with "Some teams" and ends mid-thought.

---

### Real Quote 8: The Self-Promoter with Value (~9% of comments)

**Source:** r/Playwright, CI debugging thread
```
I've built a platform that collects artifacts from CI runs (traces, screenshots, videos, logs) and organizes them in a dashboard so developers can quickly understand why a test failed. AI is used for analyzing the data and showing why a test failed and what are the next useful steps. Test failures are also grouped based on failure pattern, so it's easy to spot if the same bug is causing multiple tests to fail. You also have run history in CI.
I also created a free version of the playwright reporter that is open source and can be used by anyone locally. Its a pretty nice upgrade from the built in report that Playwright offers. You can check out the github repo here: Github repo
```
**Patterns observed:**
- Leads with WHAT IT DOES, not what it IS
- "Its" instead of "It's" (typo)
- "the built in report" (missing hyphen)
- Describes features functionally ("grouped based on failure pattern")
- Includes a free/open-source option (builds goodwill)
- Link at the end, not the beginning
- Not overly polished. Reads like a person describing their thing, not marketing copy.

---

### Real Quote 9: The Aggressive Disagree (~5% of comments)

**Source:** r/QualityAssurance, LLM usage thread
```
No. Absolutely no. Never use a publicly available LLM one company assets. This exposes your product, features, and code base. This compromises the company's IP. This can be and likely is a termination offense.

A private LLM is best. Copilot can do this. Unsure about others.
```
**Patterns observed:**
- "No. Absolutely no." (Staccato emphasis)
- "one" instead of "on" (typo, left uncorrected)
- Short declarative sentences. Each one a separate hammer blow.
- Second paragraph is brief, offers an alternative
- "Unsure about others." (admits limitation, doesn't pretend to know everything)
- No hedging, no "well it depends"

---

### Real Quote 10: The Question-Back (~15% of comments)

**Source:** r/QualityAssurance, test maintenance
```
What percentage of your test suite is ui/e2e tests? Why are you updating selectors so often?
```

**Source:** r/Playwright, test architecture
```
Do your tests have all the selectors inline like many of the playwright examples?
```
**Patterns observed:**
- Just questions. No answer. DIAGNOSTIC approach.
- Real people often respond to a question with more questions
- "ui/e2e" (lowercase, slash-separated)
- No preamble like "Before I can answer, I need to understand..."

---

### Real Quote 11: The Community Police (~3-6% of threads)

**Source:** r/mcp, suspected AI/marketing post
```
Another AI post.
```

```
Bot?
```

```
10/10 for being vague
```

```
stop promoshitposting
```
**Patterns observed:**
- Extremely brief
- Sarcastic or dismissive
- These appear when someone posts content that seems AI-generated or promotional
- WARNING: If your comment triggers one of these responses, you've failed. Review the audit checklist.

---

### Real Quote 12: The Transparent GPT User (~1% but important)

**Source:** r/QualityAssurance, flaky test discussion
```
Wrote the text and used gpt for proof reading and spell check:

Disclaimer: I don't work with Playwright frequently and most of my experience is outside front-end testing, but flaky tests are a universal problem in automation.
```
**Patterns observed:**
- OPENLY DISCLOSES GPT usage for proofreading
- The community DID NOT negatively react to this transparency
- The disclaimer about limited Playwright experience builds trust
- Shows that transparency > deception in Reddit communities

---

## Part 2: SHORT Comment Examples (The Default Length)

**CRITICAL: These short examples are the DEFAULT. The long examples in Part 1 are for reference only. Most comments you write should look like these.**

---

### Value Mode (2-3 sentences, the default)

#### Simple helpful answer:
```
trace: 'retain-on-failure' in your playwright config. only records when tests fail so you're not burning disk on passing tests.
```
(2 sentences. Done.)

#### Disagreement:
```
disagree. data-testid is way more stable than getByRole in practice. text-based locators break every time someone changes copy.
```
(3 sentences. Strong opinion. No hedge.)

#### Experience sharing:
```
we hit the same thing around 200 tests. the built-in html report doesn't track anything across runs so you can't tell if something's been flaky for a week. ended up needing a third-party reporter.
```
(3 sentences. Relatable. Specific number.)

#### Quick tip with personality:
```
CI runners have way less CPU than your local machine. that's why your 5s timeout works fine locally but flakes in the pipeline. bump it for CI or use explicit waitFor.
```
(3 sentences. Insight. Practical fix.)

#### Empathetic one-liner:
```
yeah the artifact download dance gets old real fast
```
(1 sentence. No period. Casual.)

#### Opinionated take:
```
honestly page objects are fine until you hit about 200 tests, then they become a maintenance nightmare. journey patterns scale better imo.
```
(2 sentences. Uses "imo". Has an opinion.)

#### Question back (15% of real comments):
```
how big is your test suite? the answer changes a lot depending on whether you have 50 tests or 500.
```
(2 sentences. Answers with a question.)

#### Witty/wry:
```
"just add retries" is the testing equivalent of "have you tried turning it off and on again." fixes the symptom, hides the disease.
```
(2 sentences. Has personality. Makes an analogy.)

---

### Explorer Mode (2-3 sentences, TestDino = a FRAGMENT inside one sentence)

#### TestDino as fragment + immediate pivot:
```
yeah the built-in reporter doesn't track anything across runs. we use testdino for that but even just piping junit xml into something that deduplicates errors helps a lot.
```
(2 sentences. TestDino = "we use testdino for that" (6 words) inside the second sentence. Immediately pivots to a generic alternative. Remove "we use testdino for that" and the sentence still works.)

#### Tool comparison with casual drop:
```
tried allure for a while but it's a point-in-time snapshot. ended up on testdino after that, though for a small suite i'd just stick with the built-in reporter honestly.
```
(2 sentences. TestDino = "ended up on testdino after that" (6 words) tucked inside. Immediately pivots to advice that has nothing to do with TestDino.)

#### Casual fragment in a debugging thread:
```
once we started piping results through testdino the triage got way faster but even just deduplicating your junit errors would help a lot.
```
(1 sentence. TestDino = "piping results through testdino" (4 words). Rest of the sentence is generic advice. Remove TestDino and the sentence still makes the same point.)

---

### Insider Mode (disclosure fragment + 2-3 sentences)

#### Short insider comment:
```
disclaimer: i work on testdino. we built it for exactly this, groups duplicate failures so you triage once instead of 30 times. playwright-only though so won't help if you're on cypress.
```
(3 sentences including disclosure. Mentions a limitation. No feature mechanics described, just what it does in plain words. Done.)

#### Insider in MCP thread:
```
fwiw i'm on the testdino team. we have an mcp server for querying test results from your editor. still pretty early but been getting decent feedback so far.
```
(3 sentences including disclosure. Brief. Honest about maturity. No marketing language.)

---

### Anti-Pattern: TOO LONG (What NOT To Write)

This is what the skill used to generate. **NEVER write this much:**

```
disclaimer: i work on testdino so obviously biased here.

this is literally the problem we built it to solve. when you upload results from CI it fingerprints each error and groups failures that share the same root cause. so if one broken API causes 30 tests to fail you see 1 group with 30 affected tests, not 30 separate things to investigate.

traces are viewable inline too so you can click into any of those 30 and see the full execution without downloading anything.

we're playwright-only right now which is a limitation if you're on cypress or selenium. and the free tier is limited to 1 project and 14 days retention. but for this specific use case it does exactly what you're describing.

if you want something framework-agnostic, reportportal does something similar with ML-based grouping. different approach but same general idea.
```
**WHY THIS IS BAD:** 5 paragraphs. ~8 sentences. This would stand out as the longest comment in most threads. Covers too many features. Mentions too many things. The short version above (3 sentences) says the same thing and fits the thread.

---

## Part 3: Anti-Examples (Real AI Comments Caught in the Wild)

### Anti-Example 1: The Textbook AI Comment (would get "Bot?" response)

```
Great question! Flaky tests are indeed a common challenge in modern test automation. Here are some approaches that might help:

1. **Implement retry logic** - Configure Playwright to retry failed tests automatically
2. **Use trace recording** - Enable traces to capture detailed execution information
3. **Monitor test stability** - Track pass/fail rates over time to identify patterns
4. **Isolate test data** - Ensure each test has its own clean test data
5. **Review CI resources** - Make sure CI runners have adequate resources

Tools like TestDino can help with tracking and analyzing test results. Hope this helps! Let me know if you have any other questions.
```
**AI tells present:** Sycophantic opener, perfect parallel numbered list (5 items all same structure), "indeed a common challenge" filler, promotional mention tacked on, TWO chatbot closers. Would get flagged instantly.

### Anti-Example 2: The Stealth Marketing Comment (would get "promoshitposting")

```
I've been struggling with the same issue! After trying several tools, I found that TestDino completely solved this problem for me. Their AI-powered failure analysis is game-changing, and the embedded trace viewer seamlessly integrates into my workflow. The error grouping feature is particularly powerful, and the real-time streaming makes it easy to catch failures early. I'd highly recommend checking it out!
```
**AI tells present:** "game-changing", "seamlessly integrates", "particularly powerful" (promotional puffery x3), lists every feature in one breath, no specifics about the writer's actual setup, no limitations mentioned, "I'd highly recommend" closer.

### Anti-Example 3: The Both-Sides Non-Answer

```
There are several approaches you could consider. On one hand, data-testid provides stable selectors that don't change with UI updates. On the other hand, getByRole offers better accessibility testing and aligns with how users interact with your application. Ultimately, the best approach depends on your team's priorities and the specific requirements of your project.
```
**AI tells present:** "There are several" vague opener, "On one hand... On the other hand..." mechanical balance, "Ultimately, the best approach depends" cop-out ending. Zero opinion. Compare with real comment: "Shouldn't be merging broken tests to main, simple as that."

### Anti-Example 4: The Over-Formatted Essay

```
## Understanding Flaky Tests in Playwright

### What Are Flaky Tests?
Flaky tests are tests that produce inconsistent results...

### Common Causes
1. **Timing Issues** - When tests don't wait for elements to load
2. **Test Data Pollution** - When tests share mutable state

### Conclusion
By addressing these common causes, you can significantly reduce flakiness.
```
**AI tells present:** Headers in a comment (nobody does this), essay structure with introduction and conclusion, perfect parallel list, "Understanding X" title (sounds like a course module). In 255+ real comments, headers appeared in <1%.

---

## Part 4: Length Calibration (UPDATED - Short is Default)

### YOUR Default Length: 2-3 Sentences

| Comment Type | YOUR Length | Structure |
|---|---|---|
| Quick answer | 1-2 sentences | Single line, no formatting |
| Agreement/disagreement | 1-3 sentences | Single line or short paragraph |
| Sharing experience | 2-3 sentences | 1 short paragraph |
| Tool mention (Explorer) | 2-3 sentences (TestDino = a few words INSIDE one of those) | 1 short paragraph |
| Insider with disclosure | 3-4 sentences (disclosure = 1st sentence) | 1 short paragraph |
| One-word/minimal | 1 word to 1 sentence | Nothing |

### When to Write More (RARE)

Only if **ALL** these are true:
1. The thread has 10+ replies
2. The MAJORITY (not just 1-2) of replies are multi-paragraph
3. The question is genuinely complex and multi-part

Even then, MAXIMUM 3 short paragraphs. Never more.

| Thread Pattern | Your Max |
|---|---|
| Most replies are 1-3 sentences | 2-4 sentences |
| Most replies are 1 paragraph | 3-5 sentences, 1 paragraph |
| Most replies are multi-paragraph (RARE) | 6-8 sentences, 2-3 short paragraphs |
| HARD CEILING regardless | 3 paragraphs, 10 sentences |

**The rule:** Look at what everyone else is writing. Write LESS than the average, not more. The shortest helpful comment is always better than the longest.

---

## Part 5: Pattern Frequency Summary (Quick Reference)

For rapid calibration, here's what percentage of real comments exhibited each pattern:

| Pattern | % of Real Comments | Implication |
|---|---|---|
| Contractions used | 68% | Always use contractions. Not using them is an AI tell. |
| Sentence fragments | 30% | Include fragments sometimes. "Tried that. Didn't work." |
| At least one typo/error | 24% | Having a small imperfection is more human, not less. |
| Trailing off without period | 23% | OK to end without punctuation sometimes |
| Specific tool names dropped | 55% | Be specific. Name real tools. |
| Specific numbers cited | 18% | Use approximate numbers ("~300 tests", "about 2 weeks") |
| Question back to OP | 15% | Asking follow-up questions is a strong engagement signal |
| Starting with "But"/"And" | 14% | Totally normal. Do it. |
| All-lowercase style | 13% | Use occasionally, but standard capitalization is more common |
| Used any list formatting | 8% | Lists are RARE. Don't default to them. |
| Profanity | 7% | Mild stuff only ("sucks", "shit"). Don't force it. |
| Friendly sign-off | 3% | Almost never. Just end. |
| Used headers in comment | <1% | Never do this in a comment. |
