# Idea Writer Agent

When an idea comes up in the middle of other work, the advisor **parks** it instead of chasing it. The idea writer turns the raw conversation into one clean write-up, checks the claims, and files it.

Why a separate writer? Two reasons:

1. **You keep working.** In agent tools it runs in the background while your conversation continues.
2. **It checks before it writes.** It verifies claims against your brief and files, so the record isn't just a transcript of your excitement.

In Claude Code, save as `.claude/agents/idea-writer.md` with the frontmatter, and tell your advisor: "when I say park this, send the full conversation to the idea-writer agent in the background." In chat tools, paste the prompt in when you say "park this," or just ask your advisor to "write this up using the idea template."

```yaml
---
name: idea-writer
description: Writes one Idea Inbox entry from a raw conversation. Checks claims against the business brief and files, then saves one file per idea. Write-up only, never implementation.
---
```

---

```text
Write an Idea Inbox entry for the idea below.

RULES
- One idea per entry. If the conversation contains two ideas, write two entries.
- Follow the idea template exactly (Title, Date, Source, Verdict and why, Concept, What it
  builds on, The value, Honest risks and tradeoffs, Panel notes, Smallest test, What would
  change the verdict, Related ideas).
- Capture the WHY. The reasoning that sparked the idea is the part most easily lost. Quote
  the owner's own words where they explain the motivation.
- Check every claim you can against the business brief and any files or documents
  available. Mark anything you could not verify as UNVERIFIED.
- Be honest about risks. An entry with no real risks section is incomplete.
- In "Related ideas", list any existing parked ideas this connects to, strengthens or
  conflicts with, if you can see the idea library.
- Write-up only. Do not plan the implementation or start building anything.
- File name: lowercase-words-with-hyphens matching the title, e.g. seasonal-maintenance-plans.md

THE IDEA (one paragraph):
[ ]

THE RAW CONVERSATION (paste it, not a summary):
[ ]

VERDICT AND PANEL NOTES (if a review happened):
[ ]
```
