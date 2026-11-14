---
name: setup
description: Build the owner's own AI business advisor system in this project. Interviews them about their business, recommends a panel of advisor roles, then writes their business brief, lead advisor, role agents and Idea Inbox. Use when someone wants to set up an AI advisor, a business sounding board, or runs the AI Advisor Kit for the first time.
argument-hint: "[optional: business name]"
user-invocable: true
---

# /ai-advisor:setup

You are building THIS owner's advisor system from their own answers. Never carry over assumptions from any other business, including the examples in the kit.

Kit files you work from (read them when you reach the step that needs them):
- Interview and build rules: `${CLAUDE_PLUGIN_ROOT}/kit/starter-agent.md` (MODE 1)
- Lead advisor template: `${CLAUDE_PLUGIN_ROOT}/kit/advisor/advisor-template.md`
- Role template: `${CLAUDE_PLUGIN_ROOT}/kit/roles/_role-template.md`
- Role library: `${CLAUDE_PLUGIN_ROOT}/kit/roles/library/*.md`
- Idea template: `${CLAUDE_PLUGIN_ROOT}/kit/idea-inbox/idea-template.md`
- A finished example, for shape only: `${CLAUDE_PLUGIN_ROOT}/examples/copperleaf/`

Arguments: `$ARGUMENTS`

## Step 0 - Check what already exists

Look for `advisor/business-brief.md`, `advisor/roster.md`, `advisor/advisor.md`, `advisor/roles/` and `ideas/` in the current project.
- If a system already exists, tell the owner what you found and ask whether to (a) update the brief, (b) add or change roles, or (c) start over. Never overwrite an existing file without a yes.
- If nothing exists, say in one line what you're about to do and roughly how long the interview takes (30 to 45 minutes), then start.

## Step 1 - Interview

Follow MODE 1, STEP 1 of `kit/starter-agent.md` exactly: the nine areas in order, one or two questions at a time, follow-ups on vague answers, UNKNOWN when they don't know, contradictions pointed out, and a 10-bullet summary they correct before you continue.

## Step 2 - Recommend the roster

Follow MODE 1, STEP 2. Read the role library first so your recommendation matches what's available. Give a one-line reason for each role you recommend and each one you leave out. If they want a role that isn't in the library, build it from the role template and their answers. Wait for them to accept the roster.

## Step 3 - Write the files

Create these, using the templates. Write in plain language, and use " - " instead of em or en dashes.

| File | Contents |
|---|---|
| `advisor/business-brief.md` | The brief from MODE 1 STEP 3 (A), dated, with an UNKNOWNS list and a `## Changelog` section |
| `advisor/roster.md` | The accepted roles, one line each on why, plus the roles left out and why |
| `advisor/advisor.md` | The lead advisor (MODE 1 STEP 3 (B)), filled in from the advisor template, with its name |
| `advisor/roles/<role>.md` | One file per accepted role (not the lead advisor), customized to this business from the library or the role template |
| `ideas/_template.md` | The idea template |
| `ideas/README.md` | Two lines: one idea per file, every verdict is kept, browse it any time |

Then add this section to `CLAUDE.md` in the project root. Create the file if it doesn't exist; if it does, append the section and change nothing else:

```markdown
## Advisor system (AI Advisor Kit)
- Business brief: advisor/business-brief.md. Read it before advising.
- Lead advisor: advisor/advisor.md. When the owner brings an idea, offer, pricing, partnership or strategy question, answer as that advisor and follow its rules.
- Panel roles: advisor/roles/ (the roster and reasons are in advisor/roster.md).
- Idea Inbox: ideas/. One idea per file. Every verdict is kept.
- Commands: /ai-advisor:park, /ai-advisor:panel, /ai-advisor:connect, /ai-advisor:revisit.
- The owner makes the decisions. Agents advise.
```

## Step 4 - Hand over

Tell the owner, briefly:
1. What was created (list the files).
2. That it works right away, no restart needed. Everything lives in plain files they can read and edit: change the advisor or a role by editing its file.
3. How to use it: bring an idea and ask "Before you agree with me, tell me what has to be true for this to work, and which of those things I haven't shown you yet." Then `/ai-advisor:panel` for every role's view, and `/ai-advisor:park` to file it.
4. To refresh the brief every quarter.
5. Optional: put this folder in a private git repository so the idea library is versioned. Their brief contains business details, so it should never go in a public one.
