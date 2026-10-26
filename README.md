# illuni plugins

Plugins from [illuni](https://github.com/illunidev) for Claude Code and Codex.

## UMZiK

Use [UMZiK](https://umzik.com) — turn one photo into a looping animation — from your AI agent.
The plugin connects to the remote MCP server `https://mcp.umzik.com/mcp`; you sign in with your UMZiK account (Google · Kakao) once.

## Claude Code

```
/plugin marketplace add illunidev/illuni-plugins
/plugin install umzik@illuni
```

Then run `/mcp` and choose **umzik → Authenticate**.

## Codex

Plugins → Add → **Add plugin marketplace** → Source `illunidev/illuni-plugins`, then install **UMZiK**.

Or from the CLI: `codex plugin marketplace add illunidev/illuni-plugins`.

## ChatGPT · Claude (web/app)

Add a custom connector with the URL `https://mcp.umzik.com/mcp`.

## Tools

| Tool | What it does |
|---|---|
| `list_templates` | Motion templates and sets |
| `get_credits` | Remaining credits |
| `upload_image` | Upload a photo (public URL, or a one-time upload link) |
| `create_animation` · `create_animation_set` | Create — **spends credits** |
| `get_animation` · `get_animation_set` · `list_my_animations` | Status and results |

Disconnect anytime on the web: My page → More → Connected AI apps.
