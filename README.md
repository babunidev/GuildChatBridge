# GuildChatBridge

**By:** Babuni

This is my early World of Warcraft guild-chat experiment, originally called **GuildChatAI**. I renamed its GitHub repository to **GuildChatBridge** because its existing functionality is about capturing guild messages and sending manually supplied text, not generating responses with AI. It stores received guild messages and roster names, and `/gcai <message>` forwards supplied text to guild chat. There is no demonstrated real AI integration: no model request, response generation, external bridge, credentials, or automatic reply loop exists in the inspected source.

The repository is now [GuildChatBridge](https://github.com/babunidev/GuildChatBridge), but the installed addon still uses `GuildChatAI.lua`, `GuildChatAI.toc`, `GuildChatAIDB` and the `/gcai` command. The repository rename did not change these identifiers.

## Installation and use

Install `GuildChatAI.toc` and `GuildChatAI.lua` directly under `Interface/AddOns/GuildChatAI/`, restart the client and enable the addon. The manifest targets interface 11200, but compatibility is unverified.

`/gcai hello` attempts to send `hello` to GUILD. It does not ask an AI to compose it. Empty input prints usage. Received guild messages are appended to `GuildChatAIDB.guildMessages`; roster names are stored in `guildRoster`. Chat history and player names are retained locally; no export or deletion UI is implemented.

## Limitations and verification

- Validate Lua syntax, addon varargs and callback argument conventions against the intended 1.12 client; interface 11200 alone does not establish compatibility.
- Check `%f` timestamp handling, saved-variable initialization timing and malformed existing DB tables.
- Check whether calling `GuildRoster()` inside its update event causes repeated requests/events.
- Verify guild membership and send failures; the command prints confirmation after requesting a send, without delivery acknowledgement.
- Decide retention and clearing behavior before extended use; storage grows without a bound and printed text does not ensure disk chat logging.

## Evidence and status

Reviewed on 2026-10-26 against `main` at [c66af0e](https://github.com/babunidev/GuildChatBridge/commit/c66af0eb34e76dd00ee077a8f41fbbc55f4b5523). Current Lua, TOC, README and dated commit history were inspected. Source describes implementation; it does not establish successful operation. Historical intent is reconstructed only where labeled. No in-client test or automated test was executed during this documentation pass.

## Documentation

- [Concept](CONCEPT.md) · [Design](docs/DESIGN.md) · [Content](docs/CONTENT.md)
- [Architecture](docs/ARCHITECTURE.md) · [Decisions](docs/DECISIONS.md)
- [Roadmap](ROADMAP.md) · [Changelog](CHANGELOG.md) · [Development journal](docs/DEVLOG.md)
- [AI collaboration](docs/AI_COLLABORATION.md) · [Contributor instructions](AGENTS.md)

The [historical README](docs/HISTORICAL_README.md) is retained verbatim as prior documentation, including any outdated claims. Current source and the qualifications above take precedence.
