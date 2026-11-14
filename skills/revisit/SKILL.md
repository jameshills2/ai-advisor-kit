---
name: revisit
description: Revisit a parked idea in the Idea Inbox. Checks whether the signal in its "What would change the verdict" line has happened, what has changed in the business since, and gives an updated verdict. Lists ideas that are due when no idea is named. Use when the owner says "revisit", "is it time for", or asks about an old idea.
argument-hint: "[idea file or title, or leave blank to list ideas due]"
user-invocable: true
---

# /ai-advisor:revisit

Arguments: `$ARGUMENTS`

## No idea named
Read the frontmatter of every file in `ideas/` and list:
- Ideas whose `revisit` date has passed
- NOT NOW and NOT THIS WAY ideas, oldest first
- UNREVIEWED ideas

Ask which one to look at. Don't push the owner to clear the list; the library is for browsing, not a backlog.

## An idea named
1. Read the idea file and `advisor/business-brief.md`, including its changelog.
2. Check the idea's "What would change the verdict" line. Has it happened? Ask the owner for anything you can't know from the files.
3. Note what else has changed in the business since the idea was parked, and any newer parked ideas that relate to it.
4. Give an updated verdict (it can stay the same) and the reason.
5. Ask before editing the file. If the owner agrees, update the frontmatter (`verdict`, `revisit`) and add a line at the end:
   `History: YYYY-MM-DD - was <old verdict>, now <new verdict> because <reason>.`
   Change nothing else in the file.
