# GuildChatBridge — development journal

**Project author and creative direction:** Babuni

## Evidence-based retrospective — 2026-10-26

- **2025-08-20** — [bd6afe4](https://github.com/babunidev/GuildChatBridge/commit/bd6afe4ab9b9c306ea234525aeef2f67a1617e0d): Initial Lua upload contains the message capture, roster refresh and manual-send paths; inspected diff demonstrates no model integration.
- **2025-08-20** — [244f603](https://github.com/babunidev/GuildChatBridge/commit/244f60387b01cc14188b029fb3bc2b7d67f46216): Manifest added, as recorded by the commit list; no release number is declared.

## Present implementation and interpretation

A guild-chat capture and manual-send experiment for WoW. It stores received guild messages and roster names, and `/gcai <message>` forwards supplied text to guild chat. There is no demonstrated real AI integration: no model request, response generation, external bridge, credentials, or automatic reply loop exists in the inspected source.

The observable interaction separates capture from deliberate manual transmission. A possible future AI-assisted guild interface is a reconstruction from the name, manifest notes and source comment; it is not a delivered feature or recovered approval. The original README description, “a very secret guild chat project”, is preserved in the historical record below.

Printed copies may help a player inspect messages, but a source comment claiming they ensure `WoWChatLog.txt` output is not proof that client file logging is enabled. Roster snapshots contain names only, not ranks, membership history or a conversation model.

## Evidence and status

Reviewed on 2026-10-26 against `main` at [c66af0e](https://github.com/babunidev/GuildChatBridge/commit/c66af0eb34e76dd00ee077a8f41fbbc55f4b5523). Current Lua, TOC, README and dated commit history were inspected. Source describes implementation; it does not establish successful operation. Historical intent is reconstructed only where labeled. No in-client test or automated test was executed during this documentation pass.

## Documentation authorship

I directed the project, and I used AI assistance to inspect files and selected commit diffs, identify inconsistencies and draft documentation. Historical conversations, personal motives, prior approvals and any earlier AI involvement were not recovered or invented.

## Preserved earlier documentation

The following earlier record is retained verbatim. Statements about unavailable history or pending verification describe that earlier snapshot; the dated evidence above supplements it.

# GuildChatBridge — development record

**Author:** Babuni

## Retrospective source reconstruction — 2026-10-26

The repository preserves a small, focused WoW experiment. A guild-chat logging experiment that stores guild chat messages and guild-roster names and exposes `/gcai` to send a supplied message to guild chat. Explore using guild chat as a record and possible interface for later AI-assisted interaction. The visible implementation supplies the clearest record of how the interaction was approached: `GuildChatAI.lua` registers `ADDON_LOADED`, `CHAT_MSG_GUILD`, and `GUILD_ROSTER_UPDATE`, writes into `GuildChatAIDB` and prints captured messages; `/gcai` forwards user-provided text to guild chat. `GuildChatAI.toc` declares interface 11200.

This is a retrospective reconstruction, not a transcript of original design discussions. The current code performs message capture and transmission; no external language model call, AI generation, or working integration bridge is present in the inspected source. Its source and metadata existed before the current documentation pass; original conception and iteration dates are not recoverable from these files alone. In this pass, AI assistance organized the existing evidence into documentation, without changing gameplay or attributing the original idea to AI.

## Verification

Evidence: current `README.md`, addon `.toc` metadata and inspected main `.lua` source; no full historical conversation or runtime test was available. Test against the declared WoW client version; inspect API and Lua syntax compatibility, timestamp formatting and guild-roster event behavior; do not claim that an AI bot is implemented.

## October 31, 2026 — a clearer name

The repository is now named **GuildChatBridge**, after I renamed it from **GuildChatAI**. The current code captures guild messages and roster information and sends manually supplied text; it does not implement an AI response generator. At my request, an AI assistant revised the project documentation to reflect the rename. The original Lua and TOC filenames, `GuildChatAIDB` and `/gcai` are unchanged. This was documentation work, not a new runtime test.
