# AI Pattern Detection for Reddit Comments

Adapted from testdino-content-writer (24-pattern framework) and nexus-seo humanizer. Tuned for Reddit comment length and style. **Validated against 255+ real Reddit comments** from r/Playwright, r/QualityAssurance, r/devops, r/Claude, and r/mcp.

Every comment MUST pass all these checks before being presented to the user.

---

## Hard Kills (Any of these = rewrite the comment)

### 1. Em Dashes
**The rule:** Never use em dashes ( -- or - ) in Reddit comments. Use commas, periods, or just start a new sentence.
**Why:** Em dash overuse is the single most recognizable AI fingerprint. Real redditors almost never use them.
**Data:** Across 255+ real comments, em dashes appeared in <2% of genuine comments. They appeared in 40%+ of suspected-AI flagged comments.

### 2. Sycophantic Openers
**Kill phrases:**
- "Great question!"
- "That's an excellent point!"
- "This is really interesting!"
- "I love this approach!"
- "Absolutely!"
- "Definitely!"
- "You're absolutely right!"
- "This is a fantastic project!"
- "I completely understand your frustration!"

**Data finding:** 0% of genuine comments in our 322-page dataset opened with these phrases. The closest real opener was "Really solid advice" (1 occurrence) and "This is pretty important" (1 occurrence), but those were followed immediately by specific technical pushback, not more compliments.

**What real openers look like (from data):**
- "Shouldn't be merging broken tests to main, simple as that." (direct)
- "We went through the same evolution." (experience)
- "dude, I feel this so hard." (empathy)
- "No. Absolutely no. Never use a publicly available LLM on company assets." (blunt disagreement)
- "Sounds to me you need to prioritize fixing flakiness way more" (prescriptive)

### 3. List-Essay Structure
**The pattern:** A comment that is entirely a numbered or bulleted list with full sentences.
**Data finding:** Only ~8% of real comments used any kind of list at all. Of those, lists were SHORT (3-4 items), mixed with prose, and items had DIFFERENT structures and lengths. Nobody writes 6+ parallel bullet points with full sentences.

**What real lists look like:**
```
"Auth management sucks when compared to Cypress

Querying is limited. There're good options to query elements but building nested structural selectors is pain in the ass."
```
(Fragments, different lengths, no bullet formatting, just line breaks)

### 4. Chatbot Closers
**Kill phrases:**
- "Hope this helps!"
- "Let me know if you have any questions!"
- "Feel free to ask if you need more info!"
- "I'd be happy to elaborate!"
- "Good luck with your project!"
- "Happy to help!"

**Data finding:** ~3% of real comments had any kind of friendly closer. The ones that existed were brief ("Best of luck!") not formulaic. 97% of comments just END when the writer is done making their point.

**How real comments actually end (from data):**
- Statement of fact, period, done. (~32%)
- Trails off without a period (~22%)
- Question back to OP/community (~15%)
- Opinion/punchline (~8%)
- "Still experimenting with where that balance makes sense." (admission of limitation ~5%)

### 5. Perfect Parallel Structure
**The pattern:** Every bullet point or sentence follows the exact same grammatical structure.
**Example (bad):**
```
- Use data-testid for stable selectors
- Use fixtures for test setup
- Use API calls for authentication
- Use trace files for debugging
```

**Data finding:** 0% of real comments had perfect parallel structure in lists. Real lists are messy:
```
"You're not following selector best practices - I've found stability in using getByRole for 99% of cases. Auth management sucks when compared to Cypress. Querying is limited."
```
(Different lengths, different structures, different tones within the same answer)

### 6. Suspiciously Clean Grammar (NEW - from data analysis)
**The pattern:** A comment with zero typos, perfect punctuation, every sentence grammatically correct, consistent formatting throughout.
**Data finding:** ~27% of real comments have ZERO errors. But those "perfect" comments tend to be short (1-3 sentences) or from clearly experienced writers. A LONG comment (5+ sentences) with absolutely zero imperfections is suspicious. 24% of real comments contain at least one typo or grammatical error. Having an imperfection actually increases authenticity.

**Natural imperfections to include (from real data):**
- "its" instead of "it's" (8% of comments)
- Missing period at end of comment (23%)
- One typo in a longer comment ("supper" for "super", "instace" for "instance")
- Lowercase "playwright" instead of "Playwright" (14%)
- Comma splice instead of period
- Starting sentence with "And" or "But" (14%)

---

## Pattern Detection Categories

### Category A: Generic Openers (Remove or Rewrite)

These phrases appear disproportionately in AI output and ~0% in real Reddit comments:

```
"In today's..." (anything)
"When it comes to..."
"As someone who..."  (real people just share the experience)
"In my experience..." (AI overuses this; real people said it ~2% of the time)
"The thing about X is..."  (OK rarely, but AI overuses it)
"It's worth noting..."
"I'd recommend..."
"There are several..."
"One of the most important..."
"Here's the thing..."
```

**What real people use instead (from 255+ comments):**
```
"We use..." / "We went through..." (~20% of comments)
Direct statement: "Playwright's auto-wait doesn't cover everything." (~32%)
"tried [doing X]" / "tried a few over the past year" (~8%)
"yeah" / "ya" (~7%)
Question: "how many tests are affected?" (~8%)
```

### Category B: Filler Commentary (Delete Entirely)

These add zero information and never appeared in real comments:

```
"It is important to note that..."
"It is worth mentioning that..."
"It should be noted that..."
"Needless to say..."
"Obviously..." (when followed by something that needs explanation)
"As mentioned earlier..."
"At the end of the day..."
"The bottom line is..."
```

**Exception:** "To be fair..." appeared once in real data. OK once maximum, never twice.

### Category C: Mechanical Transitions (Replace with Natural Flow)

```
"Now, let's look at..."
"Moving on..."
"That being said..."
"Having said that..."
"With that in mind..."
"On a related note..."
"Speaking of which..."
"Another thing to consider is..."
"Additionally..." 
"Furthermore..."
"Moreover..."
```

**What real people use (from data):**
- No transition at all. Just start the next paragraph. (most common)
- "also" (very common, used casually)
- "and" / "but" / "though" at sentence start
- "one thing i'd flag:" (transitions via introducing a new point)

### Category D: Vague Qualifiers (Specify or Remove)

```
"various tools" -> name 2-3 specific tools (real people named tools in 55% of comments)
"several approaches" -> describe the specific approaches
"many teams" -> "most teams i've worked with" or a number
"significant improvement" -> "cut our debug time from 30min to 5min"
"quite useful" -> describe what specifically is useful
```

**Data finding:** Real commenters are SPECIFIC. 18% included exact numbers ("157 e2e tests", "2 people for 3 days", "95-99% pass rate"). 55% named specific tools. Vagueness is an AI tell.

### Category E: Promotional Puffery (Rewrite to Specific)

```
"game-changing" -> describe what specifically changed
"revolutionary" -> describe the specific improvement
"cutting-edge" -> describe the specific technology
"seamlessly integrates" -> describe how the integration works
"powerful features" -> name the specific features
"robust solution" -> describe what it handles
"comprehensive platform" -> describe what it covers
"streamline your workflow" -> describe the specific workflow change
```

**Data finding:** 0% of genuine comments used promotional puffery. Comments that DID use it got called out: "Another AI post.", "Bot?", "stop promoshitposting" (~3-6% of threads had community policing of suspected marketing/AI content).

---

## Sentence-Level Checks

### Opening Word Repetition
- No 2 consecutive sentences starting with the same word
- No 3 sentences in any paragraph starting with "The", "It", "This", or "I"
- If you catch yourself starting multiple sentences with "I", restructure some to drop the subject
- **Data finding:** Real people varied their sentence starters naturally. The most common starts were "I" (personal), "We" (team), "The" (technical), and "It" (reference). They rarely used the same one twice in a row.

### Length Monotony
- Not every sentence should be the same length
- Mix: short (under 10 words), medium (10-20 words), occasional long (20-30 words)
- **Data finding:** 50% of comments had a natural mix of short and long sentences. 20% were mostly short. 13% were mostly long. Only AI produces uniform 15-word sentences throughout.

### Structure Monotony
- Mix declarative statements with questions, fragments, and compound sentences
- Don't make every sentence [Subject] [Verb] [Object]
- **Data finding:** 30% of real comments contained sentence FRAGMENTS. 14% started sentences with "But" or "And". Questions appeared in 15% of comments. These break up structural monotony naturally.

---

## Reddit-Specific AI Tells

These patterns are specifically noticeable in Reddit comments. Each verified against real data:

### 1. The "Here are N things" Pattern
**AI:** "Here are 3 things that helped me with flaky tests:"
**Human:** Just starts listing them without announcing the count.
**Data:** 0 out of 255+ genuine comments used "Here are N things." One used "Three things that cause most of the flaky Playwright tests I keep seeing" as a POST TITLE, not a comment opener. In comments, people just dive in.

### 2. The Acknowledgment-Then-Answer Pattern
**AI:** "That's a really common problem. What helped me was..."
**Human:** "what worked for us was..." (skip the acknowledgment)
**Data:** ~6% of real comments opened with brief empathy ("yeah been there", "dude, I feel this so hard") but they were BRIEF and PERSONAL, not formulaic. "That's a really common problem" sounds like a customer service agent.

### 3. The Balanced Both-Sides Pattern
**AI:** "While data-testid has its benefits, getByRole offers better accessibility testing. Ultimately, it depends on your priorities."
**Human:** "i'd go with data-testid. the accessibility argument is valid but in practice text changes break getByRole selectors way more often than people admit."
**Data:** Real commenters are OPINIONATED. They pick a side. Comments like "Shouldn't be merging broken tests to main, simple as that." (~16% blunt/prescriptive tone). The "ultimately it depends" cop-out appeared in 0% of genuine comments.

### 4. The Comprehensive List Pattern
**AI:** Covers every possible aspect of the topic in a well-organized list.
**Human:** Focuses on the 1-2 things that actually matter and skips the rest.
**Data:** Real long comments tell a STORY ("We went through the same evolution. Started with X, then tried Y, ended up on Z.") rather than covering all options systematically. Only OP posts sometimes attempt comprehensive coverage.

### 5. The Disclaimer Pattern
**AI:** "Of course, your mileage may vary, and it's important to evaluate based on your specific needs."
**Human:** Doesn't add disclaimers. States their opinion and moves on.
**Data:** The closest thing to a disclaimer in real data was "Not trying to sound rude but..." (~2%) and "Might be a hot take" (~1%). These were BEFORE the statement, as self-aware hedges, not after as generic qualifiers.

### 6. The False Modesty Pattern
**AI:** "I'm not an expert, but..." or "Take this with a grain of salt, but..."
**Human:** Just says the thing. Doesn't pre-qualify.
**Data:** A few real commenters used "I'm not a frontend eng" or "most of my experience is outside front-end testing" but these were SPECIFIC disclaimers about their background, not generic modesty. They still stated their point confidently after.

### 7. The Community Policing Pattern (NEW - from data)
**Real threat:** 3-6% of threads contained someone calling out suspected AI or marketing content:
```
"Another AI post."
"Bot?"
"stop promoshitposting"
"10/10 for being vague"
```
**What triggers it:** Comments that are too clean, too comprehensive, mention a product without personal context, or read like marketing copy. One commenter even disclosed: "Wrote the text and used gpt for proof reading and spell check" before their comment. The community RESPECTS transparency and PUNISHES perceived deception.

---

## Cross-Comment Consistency Check (NEW)

If writing multiple comments in a thread or across threads, maintain consistency:

**Real users are consistent in:**
- Their capitalization style (lowercase writers stay lowercase)
- Their tone (blunt writers stay blunt)
- Their formatting choices (no-format writers don't suddenly use headers)
- Their level of detail (brief writers don't suddenly write essays)

**Red flag:** A comment that uses all-lowercase casual style in one paragraph and perfect formal grammar in the next. Pick one voice and stick with it.

---

## Final Audit Checklist

Before presenting the comment, verify:

- [ ] Zero em dashes
- [ ] No sycophantic opener
- [ ] No chatbot closer
- [ ] No "Here are N things" pattern
- [ ] No perfect parallel lists
- [ ] No more than 1 filler phrase (ideally 0)
- [ ] No mechanical transitions ("Furthermore", "Additionally", "Moreover")
- [ ] No vague qualifiers ("various", "several", "many")
- [ ] No promotional puffery ("game-changing", "seamlessly", "robust")
- [ ] Opening word variety (no 2 consecutive same-start sentences)
- [ ] Sentence length variety (not all same length)
- [ ] Structure variety (not all Subject-Verb-Object)
- [ ] Sounds like a real person when read aloud
- [ ] Has at least one "imperfection" (contraction, fragment, dropped subject, trailing period)
- [ ] Proportional to the thread (not a 500-word response to a simple question)
- [ ] Doesn't cover every possible angle (focuses on what matters)
- [ ] Has an opinion (not balanced-both-sides neutral)
- [ ] Formatting is minimal (no bold + bullets + headers combo)
- [ ] Not suspiciously clean (if 5+ sentences, include at least 1 natural imperfection)
- [ ] Consistent voice throughout (don't mix casual and formal in same comment)
- [ ] Wouldn't trigger community policing ("Bot?", "AI post", "promoshitposting")
