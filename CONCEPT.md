# GuildChatBridge — concept

**Project author and creative direction:** Babuni

I originally explored guild-chat capture and manual message sending in WoW. The repo now carries the name **GuildChatBridge**, which better describes the functionality visible in the source. It stores received guild messages and roster names, and `/gcai <message>` forwards supplied text to guild chat. There is no demonstrated real AI integration: no model request, response generation, external bridge, credentials, or automatic reply loop exists in the inspected source.

The observable interaction separates capture from deliberate manual transmission. A possible future AI-assisted guild interface is a reconstruction from the name, manifest notes and source comment; it is not a delivered feature or recovered approval. The original README description, “a very secret guild chat project”, is preserved in the historical record below.

Printed copies may help a player inspect messages, but a source comment claiming they ensure `WoWChatLog.txt` output is not proof that client file logging is enabled. Roster snapshots contain names only, not ranks, membership history or a conversation model.

## Evidence and status

Reviewed on 2026-10-26 against `main` at [c66af0e](https://github.com/babunidev/GuildChatBridge/commit/c66af0eb34e76dd00ee077a8f41fbbc55f4b5523). Current Lua, TOC, README and dated commit history were inspected. Source describes implementation; it does not establish successful operation. Historical intent is reconstructed only where labeled. No in-client test or automated test was executed during this documentation pass.

## Preserved earlier documentation

The following earlier record is retained verbatim. Statements about unavailable history or pending verification describe that earlier snapshot; the dated evidence above supplements it.

# GuildChatBridge — concept

**Author:** Babuni

## Existing idea

A guild-chat logging experiment that stores guild chat messages and guild-roster names and exposes `/gcai` to send a supplied message to guild chat.

## Intended experience

Explore using guild chat as a record and possible interface for later AI-assisted interaction.

## Boundaries

The current code performs message capture and transmission; no external language model call, AI generation, or working integration bridge is present in the inspected source.

## Evidence status

Evidence: current `README.md`, addon `.toc` metadata and inspected main `.lua` source; no full historical conversation or runtime test was available.
