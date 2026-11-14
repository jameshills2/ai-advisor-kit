---
name: park
description: Park an idea in the Idea Inbox without derailing the current work. Sends the conversation that sparked it to the idea-writer agent in the background, which checks the claims and writes one file in ideas/. Use when the owner says "park this", "save this idea", "write this up for later" or similar.
argument-hint: "[optional: one-line summary of the idea]"
user-invocable: true
---

# /ai-advisor:park

Arguments: `$ARGUMENTS`

1. Identify the idea. Use the arguments if given; otherwise take it from the recent conversation. If there are two ideas, park them separately. If it's unclear which idea is meant, ask in one line.
2. If the idea is trivial (one sentence, no real decision in it), say so and offer to just note it instead of filing it.
3. Launch the `idea-writer` agent **in the background** so the conversation can continue. Give it:
   - THE IDEA: a one-paragraph statement.
   - THE RAW CONVERSATION: the relevant exchange, quoted, not summarized. The owner's reasons are the most important part.
   - VERDICT AND PANEL NOTES: if a review or `/ai-advisor:panel` happened, include the verdict and each role's lean. Otherwise say "not reviewed".
4. Tell the owner in one line that the idea is being parked, then carry on with what you were doing.
5. When the agent reports back, mention the file path and any claims it marked UNVERIFIED.

If `ideas/` doesn't exist, suggest running `/ai-advisor:setup` first, or offer to create just the folder.
