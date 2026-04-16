# Anti-AI Detection: Full Framework

Self-contained 24-pattern detection framework + 7-step humanizer. All rules embedded directly in this file. No external skills or references needed.

---

## 7-STEP HUMANIZATION (Run on every post)

### Step 1: Sentence Variation
- No 2 consecutive lines starting with the same word
- No 3 lines in any section starting with "The", "It", "This", or "I"
- Mix: short (under 8 words), medium (8-15), occasional long (15-25)
- Vary syntactic forms: declarative, question, fragment, compound

### Step 2: Tone Calibration
- Developer/SDET audience = intermediate-expert level
- Max 22-word average sentence length
- Active voice default. Passive acceptable where it flows naturally.
- No hand-holding. No defining basic terms like "CI" or "flaky test."
- Be opinionated. Real practitioners pick sides.

### Step 3: AI Pattern Removal (24 Patterns)
See full 24-pattern list below.

### Step 4: Natural Flow
- No mechanical transitions. Thoughts flow through line breaks or "also", "but", "though."
- Or no transition at all. Just start the next thought.

### Step 5: Readability
- Break up walls of text with paragraph breaks (every 3-5 sentences)
- Use natural paragraph flow, not one-sentence-per-line formatting
- Normal capitalization throughout (this is LinkedIn, not a terminal)
- Mix paragraph lengths for rhythm (a short 1-sentence paragraph followed by a longer 3-4 sentence one)

### Step 6: Personalization
- "You" language puts reader in the scenario
- Show expertise through vocabulary and specifics, never credentials
- Add subtle imperfections: starting a sentence with "And" or "But", comma splices, fragments

### Step 7: Redundancy Removal
- Say it once, well. Delete repeated ideas.
- Cut anything that doesn't advance the post's single point.

---

## 24-PATTERN AI DETECTION FRAMEWORK

### Content Patterns (1-6)

**1. Significance Inflation**
Kill: "pivotal moment", "testament to", "paradigm shift", "groundbreaking", "transformative"
Fix: Describe the specific change. "Cut pipeline time by 30 minutes" not "a transformative improvement."

**2. Notability Inflation**
Kill: Listing media mentions, awards, or accolades as proof
Fix: Let the technical content prove its own value.

**3. Superficial -ing Analyses**
Kill: "highlighting the importance of", "fostering collaboration", "contributing to the ecosystem", "underscoring the need for", "showcasing the potential"
Fix: Use concrete verbs. "The team reduced failures by 60%" not "highlighting a 60% reduction."

**4. Promotional Language**
Kill: "boasts", "vibrant community", "profound impact", "game-changing", "revolutionary", "cutting-edge", "robust", "powerful", "seamlessly", "comprehensive", "all-in-one", "next-level", "best-in-class", "state-of-the-art", "innovative"
Fix: Describe what the thing DOES, not what it IS.

**5. Vague Attributions**
Kill: "Industry reports suggest", "Experts argue", "Many teams find", "Studies show"
Fix: Name the source or drop the claim. "The Playwright docs recommend..." or just state the fact.

**6. Formulaic Sections**
Kill: "Challenges and Future Prospects" pattern, "In conclusion" summaries, setup paragraphs that reframe the problem before answering
Fix: Just make your point. No preamble, no summary.

### Language Patterns (7-12)

**7. Copula Phrases**
Kill: "serves as" → "is", "acts as" → "is", "functions as" → "is"
Fix: Use the simplest verb.

**8. Negative Parallelisms**
Kill: "Not only... but also...", "Not just... but..."
Fix: State both things directly without the construction.

**9. Rule of Three Overuse**
Kill: Everything grouped in threes. "Speed, reliability, and scalability."
Fix: Use the exact number of items the point needs. Sometimes it's 2. Sometimes 4.

**10. Synonym Cycling**
Kill: Swapping words for variety ("tool" → "solution" → "platform" → "product" in one post)
Fix: Pick one word and use it consistently. Repetition is natural.

**11. False Ranges**
Kill: "From startups to enterprises", "from beginners to experts"
Fix: Be specific about who you're talking to.

**12. Elegant Variation**
Kill: Using a different word each time for the same thing to avoid repetition
Fix: Humans repeat words. "Tests" stays "tests." Don't cycle to "test cases" → "test suites" → "automated checks."

### Style Patterns (13-18)

**13. Em Dash Overuse**
Kill: ANY em dash (— or --). This is the #1 AI fingerprint.
Fix: Use a comma, period, or start a new line.

**14. Excessive Boldface**
Kill: Bolding every key term or phrase
Fix: Bold sparingly or not at all. Most high-performing LinkedIn posts use zero bold.

**15. Title Case in Body Text**
Kill: "Test Automation Best Practices" as a mid-post phrase
Fix: Normal sentence case. "test automation best practices"

**16. Inline-Header Vertical Lists**
Kill: Every point starting with a bolded header followed by a colon
Fix: Natural prose or short lines without headers.

**17. Emoji as Bullets or Decoration**
Kill: ✅ Point one / ✅ Point two / ✅ Point three
Fix: No emojis, or use one purposefully (not as bullet replacements).

**18. Curly Quotation Marks**
Kill: "smart quotes" that look different from straight quotes
Fix: Use straight quotes or no quotes.

### Communication Patterns (19-24)

**19. Chatbot Artifacts**
Kill: "Hope this helps!", "Let me know if you have questions!", "Feel free to reach out!", "Happy to help!", "I'd be happy to elaborate!", "Good luck with your project!"
Fix: End when you're done. No wrapping up.

**20. Sycophantic Tone**
Kill: "Great question!", "That's an excellent point!", "This is really interesting!", "Absolutely!", "Definitely!", "I love this approach!"
Fix: Skip the praise. Start with your actual point.

**21. Filler Phrases**
Kill: "in order to" → "to", "due to the fact that" → "because", "it is important to note that" → delete, "it is worth mentioning" → delete, "needless to say" → delete, "at the end of the day" → delete, "the bottom line is" → delete, "as a matter of fact" → delete
Fix: Delete the filler. The sentence works without it.

**22. Excessive Hedging**
Kill: "it depends on your specific needs", "your mileage may vary", "there's no one-size-fits-all", "ultimately it comes down to your requirements"
Fix: State your opinion. If you think fixtures are better than hooks, say so.

**23. Generic Conclusions**
Kill: Paragraphs that summarize what you just said. "In summary...", "To conclude...", "The key takeaway is..."
Fix: End with your strongest insight or a specific question. No summary needed for a 150-word post.

**24. Mechanical Openers/Transitions**
Kill: "In today's...", "When it comes to...", "As someone who...", "Let me share...", "I wanted to talk about...", "Furthermore", "Additionally", "Moreover", "That being said", "Having said that", "With that in mind", "On a related note", "Another thing to consider"
Fix: Start with the scenario, question, or claim. Jump in.

---

## BANNED WORD LIST (Quick Reference)

### Hard Kill Words (never use)
seamlessly, comprehensive, game-changing, powerful, all-in-one, cutting-edge, robust, revolutionary, innovative, transformative, streamline, next-level, best-in-class, state-of-the-art, leverage (→ use), utilize (→ use), optimal (→ good/better), paradigm, synergy, ecosystem (unless literally about software ecosystems), holistic, empower, impactful

### Hard Kill Phrases (never use)
"Furthermore", "Additionally", "Moreover", "That being said", "Having said that", "It's worth noting", "Needless to say", "At the end of the day", "The bottom line is", "In today's", "When it comes to", "As someone who", "Here are N things", "Hope this helps", "Let me know if", "Great question", "In order to", "Due to the fact that"

---

## 2-PASS SELF-AUDIT

Before presenting any post:

**Pass 1 — Pattern Scan:**
- [ ] Zero em dashes
- [ ] Zero words from banned list
- [ ] Zero phrases from banned list
- [ ] Zero sycophantic openers or chatbot closers
- [ ] Zero perfect parallel lists (items vary in structure/length)
- [ ] Zero "Here are N things" patterns
- [ ] Zero balanced both-sides non-answers
- [ ] Zero filler phrases
- [ ] Zero vague qualifiers ("various", "several", "many")
- [ ] Zero promotional puffery
- [ ] Opening word variety (no 2 consecutive same-start lines)
- [ ] Line length variety
- [ ] Structure variety (not all Subject-Verb-Object)
- [ ] Under word count max for post type

**Pass 2 — Read Aloud Test:**
Ask: "If I read this aloud at a dev meetup, would it sound like a real person or a language model?"
Fix whatever doesn't pass this test.
