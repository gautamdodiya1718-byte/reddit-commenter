---
name: linkedin-post
description: >-
  Write high-engagement, factual, value-driven LinkedIn posts. Auto-detects post type,
  format, tone, and length from the user's idea or content. Six types: technical education,
  TestDino product, feature announcement, industry insight, newsletter caption, series.
  Self-contained skill with embedded humanization, algorithm optimization, and engagement intelligence.
  Cross-checks TestDino claims against live docs at https://docs.testdino.com/.
  Code must be real, runnable, human-made. Zero AI tone. Zero promotional tone.
  Triggers: "write a linkedin post", "linkedin post", "create a post",
  "newsletter caption", "feature announcement", "thought leadership post",
  "write about [topic] for linkedin", "post about", "social post".
---

# LinkedIn Post Skill

This skill is SELF-CONTAINED. All intelligence, rules, humanization patterns, and engagement data are embedded in this file and its references. No external skills needed.

---

## INTELLIGENCE LAYER: AUTO-DETECTION

The skill INFERS everything from the user's input. It does NOT ask "what type of post?" or "what tone?" It reads the idea/content and decides.

### Post Type Auto-Detection

```
USER INPUT SIGNAL                              → POST TYPE
─────────────────────────────────────────────────────────────
Mentions TestDino feature + user problem       → TestDino Product
Says "new feature", "just shipped", "released" → Feature Announcement
Says "newsletter", "caption", "issue"          → Newsletter Caption
Says "episode", "part X of", "series"          → Series/Episodic
Mentions industry trend, comparison, debate    → Industry Insight
Says "opinion", "hot take", "unpopular"        → Industry Insight
Everything else (tips, patterns, how-to, code) → Technical Education
```

Tell the user your inference in ONE line: "Writing this as a Technical Education post since it's a Playwright tip." Don't ask for permission. If they disagree, they'll say so.

### Tone Auto-Detection

```
CONTENT SIGNAL                    → TONE
───────────────────────────────────────────────
Code snippet or API pattern       → Direct, educational, code-first
Problem someone hit at work       → Empathetic, relatable, story-driven
Framework comparison or debate    → Opinionated, take-a-side, conversational
Feature or product context        → Customer-story-driven, outcome-focused
Broad industry observation        → Reflective, thought-provoking
Personal learning or mistake      → Vulnerable, honest, first-person
```

### Length Auto-Detection

```
CONTENT TYPE                      → LENGTH RANGE
───────────────────────────────────────────────────
Code-focused (image carries value)→ 100-150 words text
Quick tip or single insight       → 100-150 words
Story + lesson                    → 150-200 words
Deep technical pattern            → 150-220 words max
Newsletter caption                → 50-80 words
```

**HARD RULE: Never exceed 220 words for any post type. Count before presenting. Cut if over.**

### Format Auto-Detection

```
CONTENT TYPE                      → SUGGESTED FORMAT
───────────────────────────────────────────────────────
Step-by-step pattern or tip       → Text + code screenshot image
Comparison (tool A vs B)          → Carousel/document post (3-4x engagement)
Framework or architecture         → Text + diagram/infographic image
Personal story or opinion         → Text-only
Feature with workflow             → Text + short video or screenshot
Quick insight or hot take         → Short text-only (100-300 chars = highest engagement)
```

**Suggest the format to the user.** Carousel/document posts get 3-4x higher engagement than text-only. Always recommend visual attachment when relevant.

---

## RULE #1: LENGTH IS SACRED

| Post Type | Target | Absolute Max |
|---|---|---|
| Technical Education | 120-200 words | 220 words |
| TestDino Product | 150-220 words | 220 words |
| Feature Announcement | 130-200 words | 220 words |
| Industry Insight | 120-200 words | 220 words |
| Newsletter Caption | 50-80 words | 100 words |
| Series/Episodic | 120-200 words | 220 words |

User-specified length overrides these defaults. Even if user provides a lot of context, output STAYS within limits. Trim ruthlessly. Every word earns its place.

---

## RULE #2: THE FIRST LINE WINS OR LOSES THE POST

On LinkedIn mobile, only the first ~210 characters show before "...see more." This line is 90% of the post's performance. The algorithm measures dwell time starting from whether someone stops scrolling.

**First line requirements:**
- Under 100 characters ideal
- Creates curiosity, surprise, tension, or relatability
- Specific enough to trigger "wait, what?" or "that's my life"
- NEVER generic, vague, or predictable

**8 Hook Types (rotate, never repeat same type in consecutive posts):**

1. **Curiosity gap:** "The one config change that cut our pipeline from 45 to 12 minutes."
2. **Relatable pain:** "Have you ever spent 3 hours debugging a test that only fails in CI?"
3. **Direct question:** "Where should your Playwright tests actually live?"
4. **Provocative claim:** "Writing complex XPath is the most useless skill you can master."
5. **Story opener:** "Last Tuesday our pipeline went red. Every test in the suite."
6. **Number hook:** "50 tests failed. All from the same broken endpoint."
7. **Contrast hook:** "Tests pass locally. CI says no."
8. **Challenge hook:** "Stop trying to learn all of TypeScript before writing automation."

---

## RULE #3: NO HARDCODED FORMAT

Ivan Davidov and Stefan Judis are INSPIRATIONS, not templates. See `references/ivan-patterns.md`.

Every post must feel fresh. Vary: hook type, structure, tone, ending style. If 5 posts read the same, you failed.

**CRITICAL FORMATTING RULES:**
- **Use normal capitalization.** This is LinkedIn, not a code terminal. Capitalize the first word of sentences, proper nouns, acronyms. Ivan himself uses normal capitalization in his real screenshot posts.
- **Use natural paragraph flow.** Write like you'd write a message to a colleague or a blog post paragraph. Do NOT force one-sentence-per-line formatting. That's one specific style, not a requirement.
- **Break into 2-4 paragraphs** with natural paragraph breaks. 3-5 sentences per paragraph is fine.
- **Do NOT default to Ivan's cadence.** His pattern of short. punchy. fragments. on. separate. lines. is ONE style among many. Use it rarely, not always. Most posts should read like natural prose with paragraph breaks.
- **Vary formatting across posts:** Some posts can use short lines for emphasis. Others should use flowing paragraphs. Some can mix both. The point is VARIETY.

---

## RULE #4: ZERO AI TONE (7-STEP HUMANIZATION)

Run this 7-step transformation on EVERY post before presenting:

### Step 1: Sentence Variation
- Break monotonous structures. Vary opening words, lengths, syntactic forms.
- No 2 consecutive lines starting with the same word.
- Mix short (under 8 words), medium (8-15), occasional long (15-25).

### Step 2: Tone Calibration
- Match to audience expertise (developers = intermediate-expert, no hand-holding)
- Max 22-word average sentence length for intermediate audience
- Active voice default. Passive acceptable where it flows naturally.

### Step 3: AI Pattern Removal (24-Pattern Framework)
**Content Patterns (hard kills):**
- Significance inflation ("pivotal moment", "testament", "paradigm shift")
- Superficial -ing analyses ("highlighting", "fostering", "contributing to")
- Promotional puffery ("boasts", "vibrant", "profound", "game-changing")
- Vague attributions ("Industry reports suggest", "Experts argue")
- Formulaic section patterns (don't write like a Wikipedia article)

**Language Patterns (hard kills):**
- Copula phrases: "serves as" → "is", "acts as" → "is"
- Negative parallelisms: "Not only... but also..."
- Rule of three overuse (don't always group in threes)
- Synonym cycling (don't swap words for variety's sake)
- False ranges ("from X to Y" when you mean one thing)

**Style Patterns (hard kills):**
- Em dashes (use commas, periods, or new lines)
- Excessive boldface
- Emojis as bullet points or decorative elements
- Title Case in non-title contexts

**Communication Patterns (hard kills):**
- Chatbot artifacts: "Hope this helps!", "Let me know!", "Of course!"
- Sycophantic tone: "Great question!", "Excellent point!"
- Filler: "in order to" → "to", "due to the fact that" → "because", "it is important to note" → delete
- Excessive hedging: "it depends", "your mileage may vary"
- Generic conclusions that add nothing

### Step 4: Natural Flow
- No mechanical transitions ("Furthermore", "Additionally", "Moreover", "That being said")
- Transitions happen through line breaks or natural connectors ("also", "but", "though")
- Or no transition at all. Just start the next thought.

### Step 5: Readability
- Short-long sentence mix
- No paragraph blocks longer than 3-4 lines
- Scannable in 5 seconds

### Step 6: Personalization
- Use "you" language to put the reader in the scenario
- Show expertise through vocabulary and specifics, never through credentials
- Be opinionated. Real people pick sides.

### Step 7: Redundancy Removal
- Delete repeated ideas. Say it once, well.
- Cut anything that doesn't advance the post's single point.

**2-Pass Self-Audit:**
- Pass 1: Check all 24 patterns above. Fix any found.
- Pass 2: Ask "What makes this obviously AI-generated?" Fix whatever you find.

Full checklist in `references/anti-ai-detection.md`.

---

## RULE #5: ZERO PROMOTIONAL TONE

**Litmus test:** Remove the product mention. Is the post still valuable? If no → rewrite.

For TestDino posts:
- Customer-driven framing only ("an SDET kept hitting..." not "we added...")
- TestDino mentioned in 1-2 sentences max
- Always acknowledge a limitation or alternative
- The problem scenario IS the post. TestDino is a brief resolution.

Full anti-pattern list in `references/anti-patterns.md`.

---

## RULE #6: TESTDINO = LIVE DOCS EVERY TIME

When TestDino features are mentioned:
1. WebFetch `https://docs.testdino.com/` to verify. EVERY TIME. Never cached.
2. `references/testdino-features.md` is a starting point only.
3. If unverifiable: `SUGGEST: Have tech team verify [claim]`
4. TestDino does NOT run tests. Playwright-only reporting/analytics layer.

### TestDino Mention Decision Tree

```
Is the post about test reporting, CI debugging, flaky tests, or test analytics?
├─ NO → don't mention TestDino
└─ YES
   ├─ Is it about Cypress/Selenium/non-Playwright?
   │  └─ YES → don't mention TestDino (Playwright-only)
   ├─ Are 3+ tool recommendations already in context?
   │  └─ YES → don't mention TestDino (enough noise)
   └─ Can TestDino fit naturally without feeling forced?
      ├─ YES → mention briefly (1-2 sentences, customer-driven)
      └─ NO → don't mention TestDino
```

**The Test:** Remove the TestDino sentence. Does the post still work? If NO, the mention was the point. Rewrite.

---

## RULE #7: CODE MUST BE REAL

- No pseudocode, no demo stubs, no placeholders
- Real, runnable, human-made code verified against official docs
- WebFetch `playwright.dev` or relevant framework docs to verify APIs
- WebSearch for real patterns when needed
- Natural variable names, realistic scenarios
- Code-focused posts: text SHORT (100-150 words), image carries the value

Full rules in `references/code-snippets-rules.md`.

---

## RULE #8: PERSONA BENEFITS = FELT, NOT STATED

Never write "Benefits for developers: X." Make readers FEEL it through scenarios.
Priority: Developer > QA > SDET > CTO > Team > Business (least).
See `references/persona-benefit-map.md`.

---

## RULE #9: ALGORITHM-AWARE

LinkedIn algorithm intelligence (2025-2026 data):

**What the algorithm weights (in order):**
1. Comments (15x weight over likes). Meaningful comments 15+ words.
2. Dwell time. 30-45 seconds optimal. Posts should be deep enough to hold attention.
3. Saves and sends. Content people bookmark or share privately (strongest signals).
4. Topic expertise. Algorithm identifies your "topic DNA" and distributes to relevant audiences.

**Format performance ranking:**
1. Document/carousel posts: 6.6% engagement (3-4x higher than text)
2. Multi-image posts: 6.6% engagement
3. Video: 5.6% engagement (3x more than promotional videos)
4. Text-only: baseline
5. External links: -60% reach (AVOID)

**Optimal content mix (70/20/10):**
- 70% educational/technical insights
- 20% behind-the-scenes stories and learning journeys
- 10% product updates/announcements

**Always suggest:** visual attachment (code screenshot, diagram, carousel). Never suggest external links in the post body.

---

## WORKFLOW

### Step 1: Read the user's input
Take whatever they give you: an idea, raw content, a topic, a draft. No minimum requirements.

### Step 2: Auto-detect everything
Using the intelligence layer above, infer:
- Post type
- Tone
- Length range
- Suggested format (text, image, carousel)
- Whether TestDino is relevant
- Which personas naturally benefit

Tell the user your inferences in ONE line. Don't ask for permission.

### Step 3: Verify (if needed)
- TestDino claims → WebFetch live docs
- Code → WebFetch official docs + WebSearch for real patterns
- Technical claims → verify against known facts

### Step 4: Write the post
- Pick a hook type different from the last post
- Stay within length range. Count words.
- Run 7-step humanization
- Run 2-pass self-audit for AI patterns

### Step 5: Present

```
---
Type: [auto-detected type] | Words: [count]/[max] | Format suggestion: [text/image/carousel]
---

[THE POST]

---
Verified: [what was checked] | Notes: [anything for tech review, or "None"]
```

Keep the metadata to 2-3 lines. The post is what matters.

---

## REFERENCES

All self-contained in `references/` directory:
- `anti-ai-detection.md` — 24-pattern AI detection + 7-step humanizer + full audit checklist
- `anti-patterns.md` — 12 anti-patterns with bad/good examples
- `ivan-patterns.md` — Style inspiration from Ivan Davidov + Stefan Judis (NOT templates)
- `linkedin-engagement-rules.md` — Algorithm data, hook strategies, format performance, CTA rules
- `testdino-features.md` — Verified feature registry (starting point, always verify live)
- `persona-benefit-map.md` — FEEL-based persona scenarios
- `code-snippets-rules.md` — Real code verification rules
- `playwright-verified-reference.md` — Playwright API cross-check
- `newsletter-caption-guide.md` — Teaser format (50-80 words)
- `content-bank-index.md` — Topic reference collection
