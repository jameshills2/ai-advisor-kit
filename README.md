# AI Advisor Kit

Build an AI business advisor that knows your business, pushes back on your ideas and keeps a growing library of every idea you park.

Most AI tools are built to be helpful, so they agree with you. That's comfortable and it's dangerous: an AI that cheers on a bad idea makes it feel like a good one. This kit sets up the opposite. You get an advisor whose goals line up with your business succeeding, and who shows it by asking hard questions, plus a panel of specialist viewpoints and an Idea Inbox that turns every idea (good, early, unfunded or bad) into a record you can come back to.

**You stay the decision maker.** The advisor advises. It never decides for you.

> Created by James Hills at [Flow Media Marketing](https://flowmediamarketing.com). Read the story behind it: [How To Build An AI Business Advisor That Tells You No](https://flowmediamarketing.com/blog/ai-business-advisor-that-tells-you-no.html).

---

## Pick your door

### Door 1: I've never done this before
Start in [`start-here/`](start-here/). Three short pages, no installs, no code. You'll paste one prompt into the AI tool you already use and answer its questions.

1. [What an AI advisor is (and isn't)](start-here/1-what-an-ai-advisor-is.md)
2. [Pick your tool](start-here/2-pick-your-tool.md)
3. [Your first session](start-here/3-your-first-session.md)

### Door 2: Give me the kit
Go to [`kit/`](kit/). Start with [`kit/starter-agent.md`](kit/starter-agent.md). It interviews you, recommends which advisor roles your business needs, and builds your system from the templates in this repo.

---

### Door 3: I use Claude Code
Install the kit as a plugin and let it set everything up for you:

```
/plugin install ai-advisor --marketplace jameshills2/ai-advisor-kit
```

On older versions of Claude Code, use two steps: `/plugin marketplace add jameshills2/ai-advisor-kit`, then `/plugin install ai-advisor@ai-advisor-kit`.

Then open the folder where you want your advisor to live and run `/ai-advisor:setup`. It interviews you and writes your brief, advisor, roles and Idea Inbox as plain files you can edit.

| Command | What it does |
|---|---|
| `/ai-advisor:setup` | Interview, recommended roster, and your files |
| `/ai-advisor:park` | Files the idea under discussion in the background |
| `/ai-advisor:panel` | Every role reviews an idea, then your advisor gives a verdict |
| `/ai-advisor:connect` | Checks an article, a tip or a new idea against your parked ideas |
| `/ai-advisor:revisit` | Re-tests an old idea, or lists the ideas that are due |

---

## What's in the kit

| Folder | What it does |
|---|---|
| [`kit/starter-agent.md`](kit/starter-agent.md) | The front door. Interviews you, recommends your roster of roles, generates your files. After setup, it routes "here's an idea" to the right place. |
| [`kit/advisor/`](kit/advisor/) | The lead advisor template: pushback rules, the four verdicts, and the question every idea has to answer. |
| [`kit/roles/`](kit/roles/) | A role template, a role builder ("I need a lawyer") and a library of ready-made viewpoints. Keep the ones you need, delete the rest. |
| [`kit/idea-inbox/`](kit/idea-inbox/) | The idea writer agent, the idea template, and setup guides for a folder, Notion or Google Drive. |
| [`kit/corpus-prompts/`](kit/corpus-prompts/) | Prompts that put your idea library to work: panel reviews, connecting a new idea to old ones, mining an article for opportunities, revisiting old "not now" verdicts. |
| [`kit/platform-guides/`](kit/platform-guides/) | Setup for Claude Projects, ChatGPT, Gemini and Claude Code. |
| [`examples/copperleaf/`](examples/copperleaf/) | A complete worked example for a fictional landscaping company: brief, advisor, roster and one idea for each verdict. |

## The four verdicts

Every idea review ends with one of these, plus the reason:

- **BUILD IT** - the case holds up. Here's the smallest first step.
- **NOT THIS WAY** - good idea, wrong approach. Here's the version that could work.
- **NOT NOW** - good idea, wrong time or missing pieces. Here's what would change that.
- **NOT A GOOD IDEA** - the case doesn't hold up. Here's why, so you can recognize it next time.

All four get written up and kept. A "not now" from six months ago may be a "build it" today.

## Works with

Any capable AI tool. The full version (separate agents that run in the background and save files automatically) needs an agent tool like Claude Code. The chat version (Claude Projects, ChatGPT, Gemini) does the same thinking with a little more copy and paste. See [`kit/platform-guides/`](kit/platform-guides/).

## Make it yours

Click **Use this template** (or **Code > Download ZIP**) and change anything. The roles, verdicts and templates are starting points. An advisor built from someone else's business gives someone else's advice.

## Want help?

If you'd like help adapting this for your business, or for an agency to triage client ideas, James offers consulting through [Flow Media Marketing](https://flowmediamarketing.com).

## Share what you built

Set up your own advisor, or adapted the kit for clients? [Tell us about it](../../issues/new?template=share-what-you-built.md). We feature the best ones on [Flow Media Marketing](https://flowmediamarketing.com).

## Contribute a role

Built a role others could use (a lawyer, an HR lens, a franchise expert)? See [CONTRIBUTING.md](CONTRIBUTING.md). Accepted roles carry your name.

## How to credit this kit

If you use, adapt or write about the kit, please credit it like this:

```html
Based on the <a href="https://flowmediamarketing.com/blog/ai-business-advisor-that-tells-you-no.html">AI Advisor Kit</a> by James Hills, Flow Media Marketing (CC BY 4.0).
```

Or in plain text:

> Based on the AI Advisor Kit by James Hills, Flow Media Marketing: https://flowmediamarketing.com/blog/ai-business-advisor-that-tells-you-no.html (CC BY 4.0)

## License

[CC BY 4.0](LICENSE). Use it, adapt it, share it, sell services with it. Just credit James Hills / Flow Media Marketing with a link back.
