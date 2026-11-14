---
name: connect
description: Connect something new to the owner's Idea Inbox. Takes an article, report, competitor move, something a partner mentioned, or a new idea, and checks it against the business brief and every parked idea to find what it strengthens, weakens or connects. Use when the owner shares an article or link, says "what does this mean for us", or brings an idea that might be related to an old one.
argument-hint: "[article text, link, or new idea]"
user-invocable: true
---

# /ai-advisor:connect

Arguments: `$ARGUMENTS`

1. **Get the material.** If it's a link, fetch it. If it's something heard in conversation, take the owner's description and ask one clarifying question only if it's too vague to use.
2. **Read the context.** `advisor/business-brief.md`, then the frontmatter (title, verdict, revisit, related) of every file in `ideas/`, opening any file that looks relevant.
3. **Report:**
   - **What matters for this business,** in 3 bullets, based on the brief. If nothing does, say so and stop.
   - **Strengthens:** parked ideas this gives new evidence, a new tool or new demand to, quoting each idea's "What would change the verdict" line where it applies.
   - **Weakens:** ideas a competitor, cost, rule or market change now undercuts.
   - **Connects:** two or more parked ideas that now fit together.
   - **Repeats:** if it's a new idea, whether it repeats or closely matches something already parked, and what verdict that got.
   - **New idea?** If something here is worth parking, a one-paragraph summary and a first-read verdict.
   - **Check the source:** what is the source's angle, and what would you verify before acting on it?
4. Offer `/ai-advisor:revisit` for any idea whose verdict may have changed, and `/ai-advisor:park` for any new idea.
