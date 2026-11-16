# illuni plugins

Plugins from [illuni](https://github.com/illunidev) for Claude Code and Codex. Each plugin connects your AI agent to one illuni service through a remote MCP server; details, tools and data use are in each plugin's README.

| Plugin | Service | README |
|---|---|---|
| `umzik` | [UMZiK](https://umzik.com) — turn one photo into a looping animation | [plugins/umzik](plugins/umzik/README.md) |
| `moiime` | [Moiime](https://moii.me) — create and save 3D avatars | [plugins/moiime](plugins/moiime/README.md) |

## Add the marketplace

Claude Code:

```
/plugin marketplace add illunidev/illuni-plugins
/plugin install <plugin>@illuni-plugins
```

Codex: Plugins → Add → **Add plugin marketplace** → Source `illunidev/illuni-plugins`, or `codex plugin marketplace add illunidev/illuni-plugins`.
