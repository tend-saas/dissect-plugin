# Dissect for AI apps

Use your [Dissect](https://dissecthq.com) library from any AI app: find what you saved, read it in full, answer with links back to it, and keep memory of you across apps.

This package holds one skill and one remote MCP server, with a manifest for each harness. The first time you use it, your app opens a Dissect page to approve the connection. Nothing to copy, no key to keep. It is read only unless you tick the box on that page.

## Install

| App | How |
|---|---|
| Claude Code | `claude plugin marketplace add tend-saas/dissect-plugin && claude plugin install dissect@dissect` |
| Codex | `codex plugin marketplace add tend-saas/dissect-plugin && codex plugin add dissect@dissect` |
| Gemini CLI | `gemini extensions install https://github.com/tend-saas/dissect-plugin` |
| Claude, ChatGPT | Add `https://api.dissecthq.com/api/mcp` as a custom connector. See [setup](https://dissecthq.com/mcp) |
| Cursor, VS Code | One-click links at [dissecthq.com/mcp](https://dissecthq.com/mcp) |
| Any other agent | `npx add-mcp https://api.dissecthq.com/api/mcp --name dissect -g` then `npx skills add https://dissecthq.com --skill dissect -g` |

## Try it

- Find the post I saved about pricing pages and give me the link.
- What have I saved on cold outreach? Give me the main points with links.
- Use what I saved on onboarding to draft this landing page section.

Apps that show MCP prompts also list `find_a_save`, `brief_me`, `write_from_my_saves` and `catch_up`.

## What's here

| File | Read by |
|---|---|
| `skills/dissect/SKILL.md` | Every harness |
| `.claude-plugin/`, `.mcp.json` | Claude Code |
| `plugin.json`, `mcp.json`, `.agents/plugins/` | Codex, and Cursor's Agent Plugin format |
| `gemini-extension.json` | Gemini CLI |

You can see everything a connected app did, and disconnect it, under Settings, AI apps in Dissect.
