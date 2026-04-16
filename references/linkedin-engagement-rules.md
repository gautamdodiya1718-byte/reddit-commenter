# LinkedIn Engagement Rules (Data-Backed, 2025-2026)

Self-contained engagement intelligence. All algorithm data, format performance stats, and hook strategies embedded here.

---

## LINKEDIN ALGORITHM (2025-2026)

### Signal Weights (in order of importance)
1. **Comments** — 15x weight over likes. Meaningful comments (15+ words) count more. Posts that generate discussion WIN.
2. **Dwell time** — How long users spend reading. 30-45 seconds optimal. This means the content must be deep enough to hold attention, but concise enough to finish.
3. **Saves and sends** — Content people bookmark or share privately. Strongest new signal added in 2025-2026.
4. **Topic expertise** — Algorithm identifies your "topic DNA" and distributes to relevant audiences even outside your network.
5. **Relevance over recency** — Older posts surface frequently. LinkedIn shifted from "golden hour" to "momentum model" evaluating posts over 3-8 hours.

### Three-Stage Distribution
- **Stage 1 (first 60 min):** Quality filter classifies post. Tests on 2-5% of your network.
- **Stage 2 (1-2 hours):** Engagement testing. Only 5% of underperforming posts recover after this.
- **Stage 3:** If dwell time + engagement stay high, extends to 2nd/3rd degree connections.

**Implication:** The first line must stop scrolling IMMEDIATELY. If people scroll past, Stage 1 kills the post.

---

## FORMAT PERFORMANCE (Data-Backed Rankings)

| Format | Engagement Rate | Notes |
|---|---|---|
| Document/Carousel (PDF) | 6.6% | **3-4x higher than text**. 10 slides = 30-40s dwell time. Most saved format. |
| Multi-Image | 6.6% | 1.5-3x more impressions than text |
| Video | 5.6% | 3x more than promotional videos. Up 40% YoY. |
| Text-only | Baseline | Works for strong opinions and short takes |
| External links | -60% reach | **AVOID in post body.** Put links in first comment if needed. |
| Single image | -30% vs text | Reversed from 2024. Single images now underperform. |

**Format recommendation logic:**
- Step-by-step/tutorial → suggest code screenshot or carousel
- Comparison → suggest carousel (3-4x engagement)
- Architecture/framework → suggest diagram image
- Hot take/opinion → text-only is fine
- Feature walkthrough → screenshot or short video
- **Always suggest visual attachment when relevant**

---

## THE FIRST LINE (90% of post performance)

### Mobile Reality
- First ~210 characters show before "...see more" on mobile
- You have 3 seconds to capture attention
- The hook determines if someone stops scrolling or keeps going

### First Line Requirements
- Under 100 characters ideal
- Creates one of: curiosity, surprise, tension, relatability, disagreement
- Specific enough to trigger "wait, what?" or "that's my life"
- NEVER generic, vague, predictable, or explanatory

### 8 Hook Types (Rotate Across Posts)

| # | Type | Example | Mechanism |
|---|---|---|---|
| 1 | Curiosity gap | "The one config change that cut our CI from 45 to 12 minutes." | Reader NEEDS to know what it is |
| 2 | Relatable pain | "Have you ever spent 3 hours debugging a test that only fails in CI?" | "That's me" reaction |
| 3 | Direct question | "Where should your Playwright tests actually live?" | Brain starts answering |
| 4 | Provocative claim | "Writing complex XPath is the most useless skill you can master." | Agree/disagree impulse |
| 5 | Story opener | "Last Tuesday our pipeline went red. Every test in the suite." | Narrative tension |
| 6 | Number hook | "50 tests failed. All from the same broken endpoint." | Specific numbers demand attention |
| 7 | Contrast hook | "Tests pass locally. CI says no." | Expectation vs reality gap |
| 8 | Challenge hook | "Stop trying to learn all of TypeScript before writing automation." | Challenges a belief |

### First Line NEVER Starts With
- "In today's..." / "When it comes to..." / "I wanted to share..."
- "Here are my top N..." / "Excited to announce..." / "Just published..."
- Product names or definitions
- "Have you ever wondered..." (too generic)
- Any sentence that could appear on a marketing landing page

---

## POST FORMATTING

### Capitalization & Style
- **Normal capitalization.** Capitalize sentence starts, proper nouns, acronyms. This is LinkedIn, not a terminal.
- **Natural paragraph flow.** Write like a blog post or message to a colleague. NOT one-sentence-per-line.
- 2-4 paragraphs per post. 3-5 sentences per paragraph is natural.
- Vary paragraph lengths for rhythm (a short 1-sentence break, then a 3-4 sentence one).
- Do NOT default to Ivan's one-line-per-thought style. That's one option among many.
- Most posts should read like natural prose with paragraph breaks between ideas.

### Code in Posts
- LinkedIn has no native code formatting
- For code-heavy posts: text explains WHY, attached screenshot image shows the code
- Code posts keep text shorter (100-150 words) since the image carries value
- Suggest dark-background syntax-highlighted screenshots as attachments

### Emojis & Hashtags
- Emojis: minimal. Zero is fine. If used, purposeful only.
- Hashtags: 1-3 at the very end. Never inline. Only directly relevant ones.

---

## POST LENGTH (Data-Backed)

### Optimal Ranges
- **Short-form (100-300 characters / ~20-50 words):** Highest engagement rates. Best for questions and hot takes.
- **Medium-form (1,300-1,600 characters / ~200-250 words):** Optimal for substantive content. 30-45 second read time.
- **Real-world benchmark:** Ivan's actual posts = 75-200 words. Stefan's = 50-300 words.

### Our Limits
| Post Type | Target | Absolute Max |
|---|---|---|
| Technical Education | 120-200 words | 220 words |
| TestDino Product | 150-220 words | 220 words |
| Feature Announcement | 130-200 words | 220 words |
| Industry Insight | 120-200 words | 220 words |
| Newsletter Caption | 50-80 words | 100 words |
| Series/Episodic | 120-200 words | 220 words |

---

## CONTENT MIX (70/20/10 Rule)

- **70%** educational/technical insights (tips, patterns, code, how-tos)
- **20%** behind-the-scenes stories and learning journeys (personal)
- **10%** product updates/announcements (TestDino, features)

This means: for every 10 posts, ~7 should be pure education, ~2 personal stories, ~1 product-related.

---

## ENDING THE POST

Vary endings. Never end the same way twice in a row.

**Options:**
- Specific question inviting concrete answers (drives comments, which = 15x like weight)
- One-line insight worth sharing (drives saves, which = strongest signal)
- A thought to sit with (drives dwell time)
- Dynamic CTA under 120 chars (only when relevant)
- Nothing. End when done. Not every post needs a closer.

### Good Questions (Specific, Debatable)
- "At what repo count did your team move tests to a dedicated repo?"
- "Do you enforce a locator hierarchy or let engineers choose?"
- "How many engineers on your team can actually read a Playwright trace?"

### Bad Questions (Generic, Low Value)
- "What do you think?" / "Thoughts?" / "Do you agree?"
- "Share your experience!" / "Have you tried this?"

### Dynamic CTA Rules
- One line, one sentence, under 120 characters
- Specific to the post's content
- Non-promotional. No product names as pitches.
- Not every post needs one. A good question IS the ending.

---

## ENGAGEMENT AMPLIFIERS (Natural, Never Forced)

1. **Debate-worthy claims** — split the audience. "XPath is useless" got 377 likes, 139 comments.
2. **Specific numbers** — "50 tests", "3 environments", "45 minutes." Never "many" or "several."
3. **Before/after contrast** — "went from 45 min to 12 min."
4. **Code screenshots** — readers screenshot and use immediately. High save rate.
5. **One-line quotable insights** — "Real seniority isn't mastering complex syntax. It's choosing tools that don't require maintenance."
6. **Visual attachments** — 100% of highest-performing posts have them.
7. **Learning journey vulnerability** — "I spent 3 hours on this before realizing..." Developers relate.
8. **Specificity over abstraction** — name tools, give numbers, reference real files.

---

## HASHTAG RULES

- 1-3 hashtags at the very end. Never inline.
- Only directly relevant: #Playwright, #TestAutomation, #QA
- Ivan uses 0-1. Stefan uses 0-2.
- More than 5 = spam signal. LinkedIn algorithm deprioritizes.
