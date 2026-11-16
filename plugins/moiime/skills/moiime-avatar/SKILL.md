---
name: moiime-avatar
description: Create, refine and save a 3D avatar on the user's Moiime (moii.me) account with the Moiime MCP tools. Use when the user wants to make or change a Moiime avatar, see their saved Moiime characters, or find avatar parts.
---

# Moiime avatars

The Moiime tools work on the signed-in user's own moii.me account.

## Make a new avatar

1. Call `compose_avatar` with the user's description in their own words (any language). It returns a draft and its `draftId`.
2. For each change the user asks for, call `edit_avatar` with the same `draftId` and a description of the change. Keep reusing that `draftId`; do not start a new draft unless the user asks for a different avatar.
3. Call `save_avatar` only after the user says they want to keep it. Ask for a name if they have not given one. Saving the same draft again updates the same character.

Drafts expire after 7 days. If a tool says the draft is gone, offer to start again with `compose_avatar`.

## Saved characters

- `list_my_avatars` lists saved characters with their `characterId`.
- `get_avatar` shows one of them in 3D. The preview is a watermarked copy.
- To get the file (GLB, FBX and so on), the user presses export in that 3D preview. It shows the price and charges credits only when the user confirms there. There is no tool for exporting; if the app cannot show the preview, give the moii.me link instead. `get_credits` shows the balance.

## Parts

`search_parts` finds parts (hair, top, bottom, shoes, accessories) from a description. Use it when the user wants to browse options; to put a part on a draft, describe it to `edit_avatar`.

## Without a 3D preview

Some apps cannot show the interactive preview. The tool results then include a moii.me link; give it to the user so they can open and save the avatar in the web editor.
