---
name: panel
description: Run a panel review of an idea. Each of the owner's advisor roles reviews it through its own lens, in parallel, then the lead advisor summarizes agreement and disagreement and gives a verdict (BUILD IT, NOT THIS WAY, NOT NOW, NOT A GOOD IDEA). Use when the owner asks for a panel review, wants other perspectives, or says "what does the team think".
argument-hint: "[the idea, or leave blank to use the one under discussion]"
user-invocable: true
---

# /ai-advisor:panel

Arguments: `$ARGUMENTS`

1. **The idea.** Use the arguments, or the idea currently under discussion. State it back in two sentences so every role reviews the same thing.
2. **The panel.** The roles are the files in `advisor/roles/` (reasons in `advisor/roster.md`). If that folder is missing or empty, suggest `/ai-advisor:setup`, or run the review using the lenses in `${CLAUDE_PLUGIN_ROOT}/kit/roles/library/` and say clearly that it's a generic panel, not theirs.
3. **Run the roles in parallel.** For each role file, launch a separate general-purpose agent with read-only work in mind. Give it:
   - The full text of the role file, as its instructions.
   - The path `advisor/business-brief.md`, to read first.
   - The idea, as stated in step 1.
   - This task: "Review this idea for this business strictly through your own lens. 3 to 6 bullets, the biggest risk or opportunity, what evidence would change your view, and end with your lean: support, caution or oppose. Do not edit any files."
4. **Lead advisor summary.** Then, following `advisor/advisor.md`, write:
   - Each role's lean in one line
   - Where the panel agrees
   - Where it disagrees, and which side has the better evidence
   - What has to be true, and which of those the owner hasn't shown yet
   - The smallest test
   - The verdict and why
5. If every role says "support", name the role most likely to be wrong and why. Unanimous agreement deserves a second look.
6. Offer `/ai-advisor:park` to file it with the panel notes. The owner decides; never present the verdict as a decision.
