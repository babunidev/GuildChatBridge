# GuildChatBridge — development journal

**A first-person account from the human creative.** Dates for the original motivation are reconstructed retrospectively unless tied to a commit.

## August 2025 — a small beginning (retrospective)

The experiment grew out of my interest in giving roleplayed characters a life beyond the words I typed for them. Guild chat seemed a natural place to begin: a character could listen, develop opinions and eventually contribute in their own voice while I continued controlling their adventures. The source committed on [August 20](https://github.com/babunidev/GuildChatBridge/commit/bd6afe4ab9b9c306ea234525aeef2f67a1617e0d) records only a first step—guild-message capture, roster handling and manual text sending—not the AI character I had imagined.

## October 26, 2026 — documenting what existed

An AI-assisted repository review separated visible code from the much larger ambition implied by the original name. The resulting documentation described what the Lua source attempted, noted untested client compatibility and avoided claiming that an AI response engine had been built. That work clarified the prototype, although the creative reason behind it was still missing.

## October 31, 2026 — naming the project and remembering the idea

The repository became **GuildChatBridge** instead of **GuildChatAI**, while the original installed-addon files and commands stayed as they were. Returning to the concept, I explained what had really interested me: moving through the world as my character while a second, AI-shaped voice noticed guild discussions, crafting, fights or loot and occasionally spoke for itself.

The project had gone on ice because the automatic conversation loop remained out of reach with the approach and access I was prepared to use. During this review, AI assistance also found that `SendChatMessage` and examples from 1.12-era addons undermine the blanket assumption that every guild message requires a manual Enter press. That does not solve the missing local-AI connection or the question of what a server would permit. For now, preserving the experiment and its unanswered questions feels more faithful than calling it either finished or impossible.

## Verification boundary

This journal records my account and checked repository evidence. AI assistance reviewed documentation and source; no runtime feature was added or game-client test performed in the October 31 documentation revision. The original chronology of private design discussions remains unknown.
