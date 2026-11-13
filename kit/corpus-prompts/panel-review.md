# Panel Review

Get every role's viewpoint on one idea, then a verdict from your lead advisor.

**In Claude Code**, ask the advisor to run each role agent on the idea (in parallel if it can) and summarize. **In chat tools**, paste this into your advisor project:

```text
Run a panel review on this idea: [idea]

1. Answer once for each role on my panel, using that role's lens, questions and red flags.
   Keep each role to 3 to 6 bullets and end each with its lean: support / caution / oppose.
   Stay in each role's lane; don't let them blur together.
2. Then, as my lead advisor:
   - Where does the panel agree?
   - Where does it disagree, and which side has the better evidence?
   - What has to be true for this to work, and which of those haven't I shown yet?
   - The smallest test.
   - Your verdict (BUILD IT / NOT THIS WAY / NOT NOW / NOT A GOOD IDEA) and why.
3. Ask whether I want to park it.
```

**Tip:** disagreement between roles is the useful part. If every role says "support", ask the advisor which role would most likely be wrong, and why.
