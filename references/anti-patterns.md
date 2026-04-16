# Anti-Patterns: What NOT to Do in LinkedIn Posts

Extracted from analysis of 11 current TestDino LinkedIn posts. Each anti-pattern includes a BAD example from real posts and the GOOD alternative.

---

## Anti-Pattern 1: Opening with Product Name

**BAD (from TestDino posts):**
> "TestDino shows a per-file coverage breakdown for every Playwright run, plus a diff against your baseline"

**GOOD:**
> "your pipeline says 82% covered. but what changed since last sprint? which files dropped? nobody knows until it breaks"

**Rule:** The first 3-5 lines of any post must be about the PROBLEM or SCENARIO. No product name appears before the problem is established.

---

## Anti-Pattern 2: "See How It Works" Marketing CTAs

**BAD:**
> "See how it works -->"
> "Try it free at testdino.com"
> "Link in comments"
> "Check it out here"

**GOOD:**
Dynamic CTA in one line, under 120 chars, specific to the post content:
> "how does your team track which tests flip between pass and fail?"
> "still downloading zip files from ci artifacts to debug failures?"

**Rule:** CTA must relate to the POST'S CONTENT, not the product. Never link to product pages.

---

## Anti-Pattern 3: Feature Lists Without Benefit Explanation

**BAD:**
> "TestDino provides: embedded trace viewer, error grouping, AI failure analysis, flaky test detection, real-time streaming"

**GOOD:**
> "50 tests failed. all from the same broken api endpoint. but the report shows 50 separate items. you investigate the first three, realize they're identical, and wonder how many more are duplicates."

**Rule:** Never list features. Show the WORKFLOW CHANGE through a scenario the reader recognizes.

---

## Anti-Pattern 4: Generic Engagement Questions

**BAD:**
> "What do you think?"
> "Share your experience in the comments!"
> "Have you tried this approach?"
> "What tools do you use?"

**GOOD:**
> "do you tag your describe blocks or individual tests?"
> "at what point did you stop trusting the backend docs?"
> "how many engineers on your team can actually read a playwright trace?"

**Rule:** Questions must be SPECIFIC and DEBATABLE. The reader should be able to answer with a concrete opinion, not just "yes" or "no."

---

## Anti-Pattern 5: Marketing Buzzwords

**BANNED WORDS (never use in any context):**
- "seamlessly"
- "comprehensive"
- "game-changing"
- "powerful"
- "all-in-one"
- "cutting-edge"
- "robust"
- "revolutionary"
- "innovative"
- "transformative"
- "streamline"
- "next-level"
- "best-in-class"
- "state-of-the-art"
- "leverage" (use "use")
- "utilize" (use "use")

**Rule:** If a word could appear in a product landing page headline, it doesn't belong in a LinkedIn post.

---

## Anti-Pattern 6: Hashtag Spam

**BAD:**
> #Playwright #TestAutomation #QA #SDET #Testing #DevOps #CI #ContinuousTesting #Automation #SoftwareTesting

**GOOD:**
> #Playwright #TestAutomation

**Rule:** Maximum 3-5 hashtags. Only the most relevant ones. At the very end of the post. Never inline. Ivan uses 0-1 per post.

---

## Anti-Pattern 7: No Trade-offs or Limitations

**BAD (from TestDino posts):**
Every post presents TestDino as the obvious solution with no downsides mentioned.

**GOOD (from Stefan Judis):**
> "automatic waiting certainly helps, but it does not magically eliminate flakiness. it treats symptoms rather than root causes"

**Rule:** Real practitioners discuss when something DOESN'T work. Mentioning a limitation builds trust. For TestDino posts, acknowledge at least one limitation or caveat.

---

## Anti-Pattern 8: Unverifiable Claims

**BAD:**
> "TestDino reduces triage time by 70%"
> "Teams save 5 hours per week with..."
> "The most complete reporting solution for..."

**GOOD:**
> "our team went from investigating 50 separate failures to reviewing 3 error groups. same build."

**Rule:** Every claim must be either (a) verifiable against official docs, (b) framed as a specific team's experience, or (c) flagged for tech team review. Never make statistical claims without a source.

---

## Anti-Pattern 9: "Announcing" / "We're Excited" Openers

**BAD:**
> "We're excited to announce..."
> "Announcing our new feature..."
> "Big news: TestDino now supports..."
> "We just shipped..."

**GOOD (customer-driven framing):**
> "an sdet running 400+ tests across staging and production kept hitting the same wall. traces were in ci artifacts. downloading each one took 2 minutes. multiplied by 15 failures per run."

**Rule:** Frame features as driven by real user needs. Never "announce." Tell the story of WHY it was built.

---

## Anti-Pattern 10: Wall-of-Text Formatting

**BAD:**
> "When running Playwright tests in CI environments, you often encounter situations where tests pass locally but fail in the pipeline. This is usually caused by timing differences between your local machine and the CI runner. The solution is to ensure you're using proper waiting strategies and avoiding hardcoded timeouts. Additionally, you should consider implementing retry logic and configuring appropriate timeout values for your specific environment."

**GOOD:**
> "Tests pass locally. CI says no. You check the same test, same code, same data — different result.
>
> 9 out of 10 times it's not your test. It's the environment."

**Rule:** Break up walls of text with paragraph breaks. But DON'T force every sentence onto its own line — that's a specific style choice, not a requirement. Use natural paragraph flow like you'd write in a blog post or message to a colleague. Normal capitalization. 3-5 sentences per paragraph is fine.

---

## Anti-Pattern 11: Formulaic Template Output

**BAD (the exact problem with previous skill versions):**
Every post follows the SAME structure:
> [all lowercase text]
> [one short sentence per line]
> [escalation pattern: 1 thing. 5 things. 20 things.]
> [so i did X]
> [list of solutions]
> [product mention]
> [philosophical one-liner]
> ps: [question]
> [CTA]

This includes: always using lowercase, always one-thought-per-line formatting, always ending with "ps:", always using Ivan Davidov's exact cadence.

**GOOD:**
Each post feels DIFFERENT. Vary the structure, tone, hook type, and ending. If someone reads 5 posts in a row, they should not think "these all follow a template."

**Rule:** Never produce two consecutive posts with the same structure. If the last post started with a pain scenario, start the next one with a question or a story. If the last one was 200 words, make the next one 120.

---

## Anti-Pattern 12: Exceeding Length Limits

**BAD:**
Post type says 150-220 words but the output is 265 words because "the content needed more space."

**GOOD:**
Hard stop at the max. Trim ruthlessly. Every word must earn its place. If it doesn't fit, cut a section, don't stretch the limit.

**Rule:** Count words. If over the max for the post type, CUT before presenting. No exceptions. No "slightly under target but tight and complete" in the audit.

---

## Quick Anti-Pattern Scan

Before presenting any post, scan for ALL of these:

1. Does any product name appear before the problem is established? REWRITE.
2. Does the CTA link to a product page or say "see how it works"? REWRITE.
3. Are features listed without showing the workflow change? REWRITE.
4. Is the engagement question generic ("what do you think?")? REWRITE.
5. Are any banned buzzwords present? REWRITE.
6. Are there more than 5 hashtags? REDUCE.
7. Are there zero trade-offs or limitations mentioned (for product posts)? ADD ONE.
8. Are there unverifiable statistical claims? REMOVE or SOURCE.
9. Does the post open with "announcing" or "we're excited"? REWRITE with customer story.
10. Are there paragraphs longer than 3-4 lines? BREAK UP.
11. Does this post feel like it follows a rigid template? VARY THE STRUCTURE.
12. Is the word count over the max for this post type? CUT.
