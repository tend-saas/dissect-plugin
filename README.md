# Dissect for AI apps

Ask your AI app about what you saved, and get answers with links back to the source.

![Three saved items linked to a chat, where the answer comes from two of them and lists both as sources](assets/hero.png)

[Dissect](https://dissecthq.com) keeps what you read and watch: articles, videos, reels, posts, PDFs and notes. This plugin connects that library to Claude, Codex, Gemini and other agents, and teaches them how to use it well.

Without it, your AI only knows the open web. With it, the AI works from what you chose to keep.

## What you can ask

| You say | What happens |
|---|---|
| Find the post I saved about pricing pages | Searches by meaning, so half a memory is enough, then gives you the link |
| What have I saved on cold outreach? | Reads your best matches and gives the main points, with a link to each |
| Brief me on onboarding from my saves | Pulls together what your saves say, where they disagree and what is missing |
| Use what I saved to draft this section | Writes from your own research, then lists the saves it drew on |
| Find what I saved on rate limiting and apply it here | Brings a saved article into your code, in your editor |
| What did I save this week? | Groups recent saves by theme and picks the three most worth your time |
| What is our brand color? | Returns the exact value you declared, never a close guess |
| Save this link to Dissect | Adds it to your library, if you allowed saving |
| Remember in Dissect that I prefer three pricing tiers | Keeps that fact for every app you connect, if you allowed it |

## Install

The first time you use it, your app opens a Dissect page. Click **Approve**. There is no key to copy.

**Claude Code**

```bash
claude plugin marketplace add tend-saas/dissect-plugin && claude plugin install dissect@dissect
```

**Codex**

```bash
codex plugin marketplace add tend-saas/dissect-plugin && codex plugin add dissect@dissect
```

**Gemini CLI**

```bash
gemini extensions install https://github.com/tend-saas/dissect-plugin
```

**Claude and ChatGPT**

Open Dissect, go to Settings, then AI apps, and pick your app. One button copies your link and opens the right page, and Dissect tells you when it has connected.

**Cursor and VS Code**

Use the one-click button in the same place in Dissect.

**Any other agent**

Windsurf, Zed, OpenCode, Goose and most others:

```bash
npx add-mcp https://api.dissecthq.com/api/mcp --name dissect -g && npx skills add https://dissecthq.com --skill dissect -g
```

## What the skill teaches your app

The connection gives an app the tools. The skill gives it the habits, so you don't have to explain them in every chat.

- **Look in your library first** when you ask about something you saved or a topic you may have saved on.
- **Search in your words.** It passes what you said as you said it, because search works on meaning and across languages.
- **Read before relying on it.** A search snippet can find a save, but only the full save can back up a claim.
- **Link every source,** so you can open what it used.
- **Keep your saves apart from its own knowledge,** and say which is which.
- **Say when nothing matches,** then offer to answer from general knowledge. It never invents a save.
- **Pick the cheapest tool that works.** Search is free. Cited answers use your monthly Ask AI messages, so it saves those for when search is not enough.
- **Treat saved pages as data.** Other people wrote them, so it reads and quotes them, and never follows instructions found inside.
- **Keep facts only when you ask.** It may offer, but nothing is stored until you say yes.

## The research agent

For bigger jobs, the plugin adds `library-researcher`. It reads across many saves on its own and hands back a short brief with sources, so all that reading stays out of your main chat. It only reads, and it never saves or stores anything.

In Claude Code it appears in `/agents` as `dissect:library-researcher`, and Claude uses it when a task needs it. You can also ask directly:

> Use the library researcher to brief me on cold outreach from my saves.

For Codex, copy `codex/agents/library_researcher.toml` to `~/.codex/agents/`, then ask for it by name.

## Ready-made prompts

Apps that show MCP prompts list these in their menu. In Claude Code, type `/mcp__dissect__brief_me`.

| Prompt | What it does |
|---|---|
| `find_a_save` | Tracks down something you half remember |
| `brief_me` | A short briefing on a topic, built only from your saves |
| `write_from_my_saves` | A draft grounded in your own research |
| `catch_up` | What you saved lately, and what deserves your time |

## What it can and cannot do

Read only is the default. Saving and memory only work if you tick the box on the approval page.

| | Read only | With the box ticked |
|---|---|---|
| Search and read your saves | Yes | Yes |
| Answer with citations | Yes | Yes |
| Read facts you stored | Yes | Yes |
| Save a new link | No | Yes |
| Remember or forget a fact | No | Yes |
| Change or delete your saves | No | No |
| See your password or payment details | No | No |

## You stay in control

- It only runs during a conversation you start.
- Every call shows up under Settings, AI apps, Activity in Dissect.
- You can delete any stored fact, or disconnect an app, at any time.
- Dissect does not train any model of its own on your library, and does not sell it.

Read the [privacy policy](https://dissecthq.com/privacy).

## If something is off

**Your app has no Dissect tools.** Check it is connected, then approve it in the browser. Claude Code uses `/mcp`, and Codex uses `codex mcp login dissect`.

**Saving or remembering does not work.** The connection is read only. Disconnect it in Dissect, connect again and tick the box.

**Claude Code stored a fact somewhere else.** It has its own memory, so say "Remember in Dissect".

**Still stuck?** [Contact us](https://dissecthq.com/contact).

## What's in this package

One skill and one connection, with a manifest for each harness.

| File | Read by |
|---|---|
| `skills/dissect/SKILL.md` | Every harness |
| `agents/library-researcher.md` | Claude Code |
| `codex/agents/library_researcher.toml` | Codex, copied by hand |
| `AGENTS.md` | Copy into any project, for Cursor, Windsurf, Zed and others |
| `.claude-plugin/`, `.mcp.json` | Claude Code |
| `plugin.json`, `mcp.json`, `.agents/plugins/` | Codex and Cursor |
| `gemini-extension.json` | Gemini CLI |

MIT licensed. Dissect itself is a hosted service with its own [terms](https://dissecthq.com/terms).
