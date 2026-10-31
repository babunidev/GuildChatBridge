# GuildChatBridge

**Creative direction:** Babuni  
**Status:** Paused experiment; not a functioning AI character

GuildChatBridge began with a roleplaying idea: what if my World of Warcraft character could have a voice of their own? While I controlled movement, combat and other actions, a local AI could notice what happened around the character, interpret guild conversation and occasionally speak in character. The aim was not a gameplay bot. It was an experiment in giving a player-controlled character a second, partly independent social life.

The first ambition was an AI that could read guild chat and respond there without my composing every line. Later possibilities included reactions to crafting, fighting, loot and nearby events, with party or raid conversations as possible extensions. The character should speak when something mattered to them, not fill every silence.

## Why the project is paused

The original attempt stalled because I could not complete the automatic conversation loop with the tools and access available to me. At the time, I understood sending chat to require direct player input, and did not want to rely on unsupported or intrusive workarounds.

That explanation needs one technical qualification: `SendChatMessage` exists, and this prototype itself calls it for guild chat. Available API references and examples of 1.12-era addons show that automatic chat transmission is not categorically impossible. What remains unsolved here is a **reliable, permitted, live connection between game events, an external AI and in-game speech**, including the rules of the particular server. No autonomous response loop is implemented or verified. See [architecture](docs/ARCHITECTURE.md) and [decisions](docs/DECISIONS.md).

The idea remains on ice rather than abandoned. An AI that *suggests* character-appropriate lines for me to choose from is a possible future direction, not an implemented feature or a decision to resume development. A separate roleplaying-assistant concept should not be confused with this project.

## What the repository actually contains

The installed addon still uses its original name, **GuildChatAI**. Its Lua source attempts to:

- Capture `CHAT_MSG_GUILD` messages and guild-roster names in `GuildChatAIDB`.
- Print received messages to the chat frame.
- Send text manually supplied through `/gcai <message>` using `SendChatMessage(msg, "GUILD")`.

It does **not** include an AI model, external process, network bridge, generated dialogue, automatic replies or activity-based personality. The code has not been verified in a live client during these documentation reviews.

### Installation snapshot — unverified

The source layout suggests placing `GuildChatAI.lua` and `GuildChatAI.toc` inside `Interface/AddOns/GuildChatAI/`. The manifest declares interface `11200`. Actual 1.12 compatibility and loading behavior still require testing. The slash command sends user-provided text, not AI output.

The repository name changed from `GuildChatAI` to `GuildChatBridge` on October 31, 2026. Lua and TOC filenames, `GuildChatAIDB` and `/gcai` were intentionally left unchanged.

## Documentation

[Concept](CONCEPT.md) · [Roadmap](ROADMAP.md) · [Architecture](docs/ARCHITECTURE.md) · [Experience design](docs/DESIGN.md) · [Content](docs/CONTENT.md) · [Decisions](docs/DECISIONS.md) · [Development journal](docs/DEVLOG.md) · [Changelog](CHANGELOG.md) · [AI collaboration](docs/AI_COLLABORATION.md) · [Development rules](AGENTS.md)

The [historical README](docs/HISTORICAL_README.md) remains an unmodified archival snapshot. This README describes the present understanding, not a verified release.
