# Idea Inbox: A Folder Of Files

The simplest option, and the best one for agent tools like Claude Code. Also works with Obsidian, VS Code, or any folder synced by Dropbox, OneDrive or iCloud.

## Setup

```
your-advisor/
├── brief/
│   └── business-brief.md
├── ideas/
│   ├── seasonal-maintenance-plans.md
│   ├── second-location.md
│   └── ...
└── .claude/agents/          (Claude Code only)
    ├── starter.md
    ├── advisor.md
    ├── idea-writer.md
    └── [your roles].md
```

1. Create an `ideas/` folder.
2. Each idea is one `.md` file, named after its title in lowercase with hyphens.
3. The frontmatter at the top of each file (verdict, date, revisit, related) makes the folder searchable and sortable.

## In Claude Code

Tell your advisor once, or put it in the advisor's instructions:

> When I say "park this", send the full conversation to the idea-writer agent in the background. It saves the entry to `ideas/` and checks the existing files there for related ideas.

Because the agents can read the whole folder, prompts like "check this against my parked ideas" work without any copying.

## In Obsidian

Open the folder as a vault. Links between ideas (`[[second-location]]`) become a graph you can browse, which suits non-linear review.

## Using it with chat tools

When you want the advisor to see your library, upload the relevant idea files (or all of them, if your tool allows) into the chat or project.
