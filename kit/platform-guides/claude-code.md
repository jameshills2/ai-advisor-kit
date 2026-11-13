# Setup: Claude Code (the full version)

In an agent tool, every role is a real separate agent, the idea writer can run in the background while you keep talking, and everything is saved as files the agents can read later. This is the version the kit was originally built from.

## 1. Create a folder for your advisor

```
your-advisor/
├── CLAUDE.md
├── brief/business-brief.md
├── ideas/
└── .claude/agents/
```

Or clone this repo and work inside it.

## 2. Run the starter agent

Copy `kit/starter-agent.md` (with its frontmatter) to `.claude/agents/starter.md`, start Claude Code in the folder, and say:

> Run the starter agent. Save the documents it produces as files: brief to `brief/`, the advisor, roles and idea writer to `.claude/agents/`.

## 3. Point Claude at your system

Add to `CLAUDE.md`:

```markdown
# Advisor system
- Business brief: brief/business-brief.md. Read it before advising.
- Lead advisor: the `advisor` agent. Use it for any idea, offer, pricing or strategy question.
- Panel: the role agents in .claude/agents/. For a panel review, run each role on the idea
  (in parallel where possible), then have the advisor summarize and give a verdict.
- Idea Inbox: ideas/. When I say "park this", send the full conversation to the
  `idea-writer` agent in the background and keep working. One idea per file.
- I make the decisions. Agents advise.
```

## 4. Use it

- "Here's an idea..." for an advisor review
- "Panel review" for every role's view
- "Park this" to file the idea in the background
- "Check this article against my ideas" with a link or pasted text
- "Revisit ideas/second-location.md"

## Tips

- **Commit the folder to a private git repository.** Your idea library becomes versioned, and you can see how a verdict changed over time.
- **Give roles only the tools they need.** Reviewers can usually be read-only.
- **Let the idea writer check claims against your real files.** That is the main advantage over the chat version.
- The same files work in other agent tools that support agent or instruction files; adjust the folder names to match.
