# Moiime

Use [Moiime](https://moii.me) from your AI assistant: describe a 3D avatar in plain words, refine it over a few turns of conversation, and save it to your Moiime account. You can also open the avatars you have already saved and search the parts catalog (hair, tops, bottoms, shoes, accessories).

This plugin adds two things:

- **The Moiime MCP server** — a remote server at `https://moii.me/api/mcp`, run by illuni Inc. Nothing runs on your machine.
- **The `moiime-avatar` skill** — tells Claude the order to use the tools in (draft → edit → save) and when to ask you first.

## Sign in

The first time a tool runs, your AI app opens the Moiime sign-in page (OAuth). Sign in with your moii.me account and approve the connection. The connection only gets the permissions shown on that page; you can remove it at any time by disconnecting or removing the Moiime connector in your AI app.

## Tools

| Tool | What it does | Changes data |
|---|---|---|
| `list_my_avatars` | Lists the characters saved on your account | No |
| `get_avatar` | Shows one saved character in 3D (a watermarked preview copy), with motion playback and file export | No |
| `search_parts` | Finds avatar parts from a description | No |
| `get_credits` | Shows your credit balance | No |
| `compose_avatar` | Makes a new avatar draft from a description. Drafts expire after 7 days | Creates a draft |
| `edit_avatar` | Changes a draft from a description | Updates a draft |
| `save_avatar` | Saves a draft as a character on your account. Saving the same draft again updates that character | Yes |

In apps that support MCP Apps (claude.ai, Claude Desktop), results show an interactive 3D preview; elsewhere you get text and a link that opens the avatar on moii.me.

### Credits

No tool spends credits on its own. The 3D preview of a saved character can export its file; the preview first shows the price and your balance, and credits are charged only when you press its **받기 · N 크레딧** ("Get · N credits") button. Each look is charged once per account, and downloading it again is free. Credits are bought on moii.me, not in the chat.

## Data and network use

- The plugin talks only to Moiime: the MCP server at `moii.me`.
- Avatar descriptions you send and the drafts and characters you create are stored on your Moiime account. Moiime processes descriptions with AI models to pick parts and colours.
- The 3D preview loads model files from `cdn.moii.me`, `gen.moii.me` and Moiime's Amazon S3 storage, uploads the saved 3D file there when you save, and downloads exported files from there.
- Moiime does not read your chat history or files. See the [privacy policy](https://moii.me/privacy) and [terms](https://moii.me/terms).

## Install

Claude Code:

```
/plugin marketplace add illunidev/illuni-plugins
/plugin install moiime@illuni-plugins
```

Then run `/mcp` and choose **moiime → Authenticate**.

Claude and ChatGPT web or desktop apps can also add a custom connector with the URL `https://moii.me/api/mcp`.

## Support

Guide: [moii.me/lab/mcp](https://moii.me/lab/mcp) · Contact: contact@illuni.com
