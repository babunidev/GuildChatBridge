# GuildChatBridge — architecture

**Project author and creative direction:** Babuni

`GuildChatAI.lua` creates one frame for `ADDON_LOADED`, `CHAT_MSG_GUILD` and `GUILD_ROSTER_UPDATE`. The message handler appends `{timestamp, sender, message}` records and prints a formatted copy. The roster handler clears the roster table, calls `GuildRoster()` and rebuilds a name-to-true map using `GetNumGuildMembers` and `GetGuildRosterInfo`. `/gcai` directly calls `SendChatMessage(msg, "GUILD")`.

The TOC declares account-wide `GuildChatAIDB`. Initialization uses `GuildChatAIDB or { guildMessages = {}, guildRoster = {} }` at file load; it does not validate or migrate existing table shapes. There is no retention limit, network component, queue, model layer, options window or automated test suite in the inspected tree.

## Evidence and status

Reviewed on 2026-10-26 against `main` at [c66af0e](https://github.com/babunidev/GuildChatBridge/commit/c66af0eb34e76dd00ee077a8f41fbbc55f4b5523). Current Lua, TOC, README and dated commit history were inspected. Source describes implementation; it does not establish successful operation. Historical intent is reconstructed only where labeled. No in-client test or automated test was executed during this documentation pass.

## Preserved earlier documentation

The following earlier record is retained verbatim. Statements about unavailable history or pending verification describe that earlier snapshot; the dated evidence above supplements it.

# GuildChatBridge — architecture snapshot

**Author:** Babuni

## File inventory

`GuildChatAI.lua`, `GuildChatAI.toc`, `README.md`, `LICENSE`

## Observed implementation

`GuildChatAI.lua` registers `ADDON_LOADED`, `CHAT_MSG_GUILD`, and `GUILD_ROSTER_UPDATE`, writes into `GuildChatAIDB` and prints captured messages; `/gcai` forwards user-provided text to guild chat. `GuildChatAI.toc` declares interface 11200.

## Verification boundary

This description comes from reading source and metadata; it does not establish successful operation in a live game client.
