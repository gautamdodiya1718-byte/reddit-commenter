# Subreddit Rules Reference

This file contains the rules for each target subreddit. Check this BEFORE writing any comment. Rules are hard constraints, not suggestions.

---

## r/Playwright

**Community:** Official home for playwright.dev users. 8K weekly visitors, 120 weekly contributions.

**Rules:**
1. **No Advertising** - No advertising of any kind
2. **No "low quality" posts** - Do not take a picture of a stack trace. Include the stack trace as text.

**What this means for us:**
- **Value Mode:** Safe. Share technical insights, debugging tips, framework knowledge freely.
- **Explorer Mode:** RISKY. Mentioning TestDino as "a tool I tried" could be seen as advertising depending on how it's worded. Keep it extremely subtle and only if someone is actively asking for tool recommendations. The comment must be 90%+ genuine technical value.
- **Insider Mode:** VERY RISKY. "We built testdino" is direct advertising. Only use if someone explicitly asks "has anyone built a reporter for this?" or similar direct request. Must include genuine technical insight, not just a pitch.
- **Safe topics:** Playwright config tips, debugging strategies, fixture patterns, locator strategies, CI optimization, trace viewer usage, parallel execution, test architecture.

---

## r/QualityAssurance

**Community:** Anything software QA-related. 47K weekly visitors, 1K weekly contributions.

**Rules:**
1. **No product advertising. This includes tools, courses, etc.** - This is the strictest rule for us.
2. **Be respectful and professional**
3. **No one cares about your AI idea or chatbots destroying QA**
4. **Mods are volunteers. Please be respectful to moderators.**
5. **No "Free" articles that require email signups or other personal info**

**What this means for us:**
- **Value Mode:** ONLY safe mode here. Share QA process knowledge, testing strategies, framework comparisons at a conceptual level.
- **Explorer Mode:** DANGEROUS. Even "I tried testdino and liked it" can be flagged as product advertising. Only mention tools if directly asked AND you mention several tools together as a comparison, not singling out TestDino.
- **Insider Mode:** DO NOT USE. Saying "we at testdino" is direct product advertising and will get the comment removed and possibly banned.
- **Safe topics:** QA processes, test strategy, flaky test management approaches, team workflows, career advice, framework comparisons (conceptual, not promoting specific third-party tools).
- **Rule 3 note:** Be careful about AI-related TestDino features. This sub is hostile to AI hype. If discussing AI failure analysis, keep it grounded and practical, not hype-y.

---

## r/devops

**Community:** Everything DevOps. 161K weekly visitors, 1.4K weekly contributions.

**Rules:**
1. **Submissions must include discussion information** - Can't be just a link
2. **No editorialized titles**
3. **Job postings go to /r/devopsjobs**
4. **No vendor spam** - "Although we won't mind you promoting projects you're part of, if this is your sole purpose in this reddit we don't want any of it."
5. **Low-Effort / Low-Quality Content** - No AI content, prompt dumps, stealth marketing
6. **Surveys/Polls** require moderator approval
7. **No shortened URLs**
8. **No personal info**
9. **Be excellent to each other**

**What this means for us:**
- **Value Mode:** Safe. CI/CD optimization, pipeline architecture, test infrastructure discussions.
- **Explorer Mode:** Possible IF you're a regular contributor, not just showing up to drop tool names. The "sole purpose" clause means your comment history matters. Make the comment genuinely useful with TestDino as a side note.
- **Insider Mode:** Possible with caution. Rule 4 allows promoting projects you're part of IF that's not your sole purpose. Must pair with substantial technical value. Rule 5 explicitly bans "stealth marketing" so don't pretend to be a random user if you're from the team.
- **Critical:** Rule 5 bans AI content. Our comments must pass AI detection. This is not just about sounding human, it's a literal subreddit rule here.

---

## r/Claude

**Community:** For Anthropic's Claude AI model. 403K weekly visitors, 7.4K weekly contributions.

**Rules:**
1. **Abide by the Reddit Content Policy**
2. **No Solicitation** - "This is not a place to promote your product, service, or repo. If the intent of your post is to redirect traffic to something you are affiliated with, it will be removed."
3. **No usage, pricing, or outage spam**
4. **No lazy crossposts**
5. **Keep posts Claude and Anthropic specific**

**What this means for us:**
- **Value Mode:** Safe if the topic relates to Claude + testing/QA/Playwright MCP. Share genuine experiences using Claude for test automation.
- **Explorer Mode:** RISKY. Rule 2 is clear about not redirecting traffic. If someone asks "how do you use Claude for testing?" you can mention your workflow and testdino's MCP server as part of a broader answer, but it can't be the point.
- **Insider Mode:** DO NOT USE. Rule 2 explicitly bans solicitation from affiliated people.
- **Safe topics:** Claude + Playwright MCP experiences, AI-assisted test writing, Claude Code for test automation, prompt engineering for test generation.

---

## r/mcp

**Community:** Model Context Protocol. 72K weekly visitors, 986 weekly contributions.

**Rules:**
1. **No waitlists** - No links to future services
2. **No AI generated slop** - Will result in a ban
3. **No astroturfing** - "Self-promotion is allowed with proper disclosure. Anyone caught promoting their product while pretending to be an unaffiliated user will be permanently banned."
4. **Use showcase tag to share your work**

**What this means for us:**
- **Value Mode:** Safe. Discuss MCP architecture, integration patterns, tool-building experiences.
- **Explorer Mode:** FORBIDDEN. Rule 3 explicitly bans pretending to be unaffiliated. If you mention TestDino here, you MUST disclose affiliation. No exceptions. Getting caught astroturfing = permanent ban.
- **Insider Mode:** ALLOWED and PREFERRED if mentioning TestDino. Must include clear disclosure. "Full disclosure: I work on TestDino" or equivalent. The community respects transparency.
- **Critical:** Rule 2 bans AI slop. Our comments MUST be genuinely human-sounding. This is a bannable offense here.
- **Safe topics:** MCP server implementations, TestDino MCP integration (with disclosure), AI agent patterns, tool integration workflows.

---

## Quick Decision Matrix

| Subreddit | Value Mode | Explorer Mode | Insider Mode |
|---|---|---|---|
| r/Playwright | SAFE | CAREFUL (subtle only) | RISKY (only if asked) |
| r/QualityAssurance | SAFE | DANGEROUS (multi-tool comparison only) | NEVER |
| r/devops | SAFE | OK (if substantial value included) | OK (with disclosure, not sole purpose) |
| r/Claude | SAFE | RISKY (rule 2 solicitation) | NEVER |
| r/mcp | SAFE | NEVER (astroturfing ban) | YES (mandatory disclosure) |
