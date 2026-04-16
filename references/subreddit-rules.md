# Subreddit Rules Reference

This file contains the rules for each target subreddit. Check this BEFORE writing any comment. Rules are hard constraints, not suggestions.

**Note:** Mode safety levels (SAFE/RISKY/NEVER) are product-specific and come from `CONTEXT.md`. This file contains the UNIVERSAL subreddit rules and community culture. Check `CONTEXT.md` for the mode matrix for your specific product.

---

## r/Playwright

**Community:** Official home for playwright.dev users. 8K weekly visitors, 120 weekly contributions.

**Rules:**
1. **No Advertising** — No advertising of any kind
2. **No "low quality" posts** — Do not take a picture of a stack trace. Include the stack trace as text.

**What this means for product mentions:**
- Value Mode is always safe here. Share technical insights freely.
- Explorer Mode is RISKY. Any tool mention could be seen as advertising depending on wording. Keep it extremely subtle and only if someone is actively asking for tool recommendations. Comment must be 90%+ genuine technical value.
- Insider Mode is VERY RISKY. Direct product promotion = advertising. Only use if someone explicitly asks "has anyone built a reporter for this?" or similar direct request.
- **Safe topics:** Playwright config tips, debugging strategies, fixture patterns, locator strategies, CI optimization, trace viewer usage, parallel execution, test architecture.

---

## r/QualityAssurance

**Community:** Anything software QA-related. 47K weekly visitors, 1K weekly contributions.

**Rules:**
1. **No product advertising. This includes tools, courses, etc.** — This is the strictest rule.
2. **Be respectful and professional**
3. **No one cares about your AI idea or chatbots destroying QA**
4. **Mods are volunteers. Please be respectful to moderators.**
5. **No "Free" articles that require email signups or other personal info**

**What this means for product mentions:**
- Value Mode ONLY is safe here. Share QA process knowledge, testing strategies, framework comparisons at a conceptual level.
- Explorer Mode is DANGEROUS. Even "I tried [product] and liked it" can be flagged. Only mention tools if directly asked AND you mention several tools together as a comparison, not singling out one.
- Insider Mode: DO NOT USE. Saying "we at [product]" is direct product advertising and will get the comment removed and possibly banned.
- **Safe topics:** QA processes, test strategy, flaky test management approaches, team workflows, career advice, framework comparisons (conceptual).
- **Rule 3 note:** This sub is hostile to AI hype. If discussing AI features, keep it grounded and practical.

---

## r/devops

**Community:** Everything DevOps. 161K weekly visitors, 1.4K weekly contributions.

**Rules:**
1. **Submissions must include discussion information** — Can't be just a link
2. **No editorialized titles**
3. **Job postings go to /r/devopsjobs**
4. **No vendor spam** — "Although we won't mind you promoting projects you're part of, if this is your sole purpose in this reddit we don't want any of it."
5. **Low-Effort / Low-Quality Content** — No AI content, prompt dumps, stealth marketing
6. **Surveys/Polls** require moderator approval
7. **No shortened URLs**
8. **No personal info**
9. **Be excellent to each other**

**What this means for product mentions:**
- Value Mode is always safe. CI/CD optimization, pipeline architecture, test infrastructure discussions.
- Explorer Mode is possible IF you're a regular contributor, not just showing up to drop tool names. The "sole purpose" clause means your comment history matters. Make the comment genuinely useful with the product mention as a side note.
- Insider Mode is possible with caution. Rule 4 allows promoting projects you're part of IF that's not your sole purpose. Must pair with substantial technical value. Rule 5 explicitly bans "stealth marketing" so transparency is actually SAFER than hiding affiliation.
- **Critical:** Rule 5 bans AI content. Comments MUST pass AI detection. This is a literal subreddit rule.

---

## r/Claude

**Community:** For Anthropic's Claude AI model. 403K weekly visitors, 7.4K weekly contributions.

**Rules:**
1. **Abide by the Reddit Content Policy**
2. **No Solicitation** — "This is not a place to promote your product, service, or repo. If the intent of your post is to redirect traffic to something you are affiliated with, it will be removed."
3. **No usage, pricing, or outage spam**
4. **No lazy crossposts**
5. **Keep posts Claude and Anthropic specific**

**What this means for product mentions:**
- Value Mode is safe if the topic relates to Claude + your domain (e.g., Claude for test automation, Claude + MCP).
- Explorer Mode is RISKY. Rule 2 is clear about not redirecting traffic. If someone asks a relevant question, you can mention your workflow including a tool as part of a broader answer, but it can't be the point.
- Insider Mode: DO NOT USE. Rule 2 explicitly bans solicitation from affiliated people.
- **Safe topics:** Claude + domain experiences, AI-assisted workflows, Claude Code usage, MCP integrations (generic).

---

## r/mcp

**Community:** Model Context Protocol. 72K weekly visitors, 986 weekly contributions.

**Rules:**
1. **No waitlists** — No links to future services
2. **No AI generated slop** — Will result in a ban
3. **No astroturfing** — "Self-promotion is allowed with proper disclosure. Anyone caught promoting their product while pretending to be an unaffiliated user will be permanently banned."
4. **Use showcase tag to share your work**

**What this means for product mentions:**
- Value Mode is always safe. Discuss MCP architecture, integration patterns, tool-building experiences.
- Explorer Mode is FORBIDDEN. Rule 3 explicitly bans pretending to be unaffiliated. If you mention a product you're affiliated with, you MUST disclose. Getting caught astroturfing = permanent ban.
- Insider Mode is ALLOWED and PREFERRED when mentioning a product. Must include clear disclosure. The community respects transparency.
- **Critical:** Rule 2 bans AI slop. Comments MUST be genuinely human-sounding. This is a bannable offense.
- **Safe topics:** MCP server implementations, AI agent patterns, tool integration workflows.

---

## Quick Decision Matrix

**Note:** This matrix shows the UNIVERSAL safety level based on subreddit rules. Product-specific overrides are in CONTEXT.md.

| Subreddit | Value Mode | Explorer Mode | Insider Mode |
|---|---|---|---|
| r/Playwright | SAFE | CAREFUL (subtle only) | RISKY (only if asked) |
| r/QualityAssurance | SAFE | DANGEROUS (multi-tool comparison only) | NEVER |
| r/devops | SAFE | OK (if substantial value included) | OK (with disclosure, not sole purpose) |
| r/Claude | SAFE | RISKY (rule 2 solicitation) | NEVER |
| r/mcp | SAFE | NEVER (astroturfing ban) | YES (mandatory disclosure) |
