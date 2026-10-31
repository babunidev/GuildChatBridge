# GuildChatBridge — architecture and technical limits

## Existing implementation

The repository contains `GuildChatAI.lua` and `GuildChatAI.toc`, not an external AI application. The manifest declares interface `11200` and account-wide `GuildChatAIDB`.

The Lua source creates a frame, registers `ADDON_LOADED`, `CHAT_MSG_GUILD` and `GUILD_ROSTER_UPDATE`, and attempts the following:

| Path | Observed code | Not established |
| --- | --- | --- |
| Guild messages | Appends timestamp, sender and message to `guildMessages`; prints a copy | Persistent disk chat logging or successful client execution |
| Guild roster | Clears and repopulates a name-to-true map via guild-roster functions | Stable event behavior or complete member metadata |
| Manual send | `/gcai <message>` calls `SendChatMessage(msg, "GUILD")` | Delivery acknowledgement or AI-composed text |
| Saved data | Uses `GuildChatAIDB` declared in the TOC | Safe initialization for every client/load order, retention or migration |

No network client, localhost API, model invocation, event-to-model queue, character memory, generation prompts or autonomous sending loop exists in this source. Capturing text in an addon is not equivalent to transmitting it to a local application.

## Why the intended end-to-end system is unfinished

A future implementation would need three independently working stages:

1. **Observation:** Collect only events exposed by the intended client (guild or group messages and relevant activities).
2. **AI bridge:** Transfer selected observations to a local model promptly through a supported, permitted route, then receive a response.
3. **Expression:** Show a proposed line to the player or transmit it in an allowed channel, with rate and consent controls.

These are **conceptual components**, not implemented modules. Standard SavedVariables write on logout/reload rather than serving as a continuously updated external message stream. A client addon also should not be assumed to have arbitrary file, socket or HTTP access. Both directions of any external bridge require actual verification.

## Important correction about chat sending

The existing code contains `SendChatMessage(msg, "GUILD")`. Modern WoW API documentation distinguishes guild/party/raid chat from channels requiring hardware interaction, and historical 1.12.1 addon examples describe timer-based chat messages. Thus `all in-game chat requires Enter or paste` is not a reliable general rule. Neither those references nor this source establish permission or success for a fully automatic AI character on the intended realm.

References: [SendChatMessage API](https://warcraft.wiki.gg/wiki/API_SendChatMessage), [1.12.1 automatic-message addon example](https://github.com/0ldi/AutoMessage), [SavedVariables lifecycle](https://warcraft.wiki.gg/wiki/Saved_variables).

## Client-compatibility and correctness checks

- The legacy 1.12 client uses Lua 5.0 conventions; inspect event callback parameters and `...` usage rather than assuming modern `self, event, ...` behavior.
- Check saved-variable initialization at `ADDON_LOADED`, including preexisting/malformed tables.
- Check `date("%m/%d %H:%M:%S.%f")`: fractional seconds are not safely assumed supported.
- Test whether invoking `GuildRoster()` from `GUILD_ROSTER_UPDATE` causes excess updates.
- Verify guild presence, chat permission, throttling, error handling and whether the apparent send confirmation corresponds to actual delivery.
- Set a retention/deletion policy before retaining other players' chat logs for prolonged periods.

The code was inspected as text; no in-game or automated compatibility test was run during this documentation revision.
