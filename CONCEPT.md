# GuildChatBridge — concept

**Creative:** Babuni  
**Stage:** Paused exploration

## A character with a life of their own

The idea came from enjoying roleplay while wondering whether the character could contribute more than the actions and words I explicitly chose. In the experiment I imagined, the player would still steer the character through Azeroth, but an AI would shape their conversational voice.

Guild chat was the starting point. The character could follow discussions, decide whether something interested them and respond in their own manner. Through game events, they might notice crafting, combat, items collected or changes in the surrounding world. Those observations could become small opinions, stories or remarks. Party and raid chat were possible later extensions, not established features.

The desired feeling was closer to an AI-driven NPC sharing a player's journey than a conventional command-based chatbot. Yet this was never intended to transfer gameplay control to the AI: movement and actions would remain mine.

## The interesting boundary

A character that speaks independently might feel alive, but one that talks too much, interrupts players or impersonates genuine human attention could quickly become unwelcome. Part of the experiment was finding the narrow space where that behavior might be playful and respectful of the people sharing the game.

Meaningful silence matters as much as speech. The imagined character would have interests and context rather than simply reply to every guild message. Any future design needs transparent AI participation and should respect server rules, consent, chat volume and the ability to disable responses.

## Why it stopped, and why it remains

The original vision required an end-to-end loop: observe the game, bring the observations to an AI, let the AI decide what to say and deliver the result in game. The attempt did not achieve that loop, and I set it aside rather than claim it worked or force a workaround I did not want.

The belief that all guild-chat output necessarily requires keyboard confirmation should not be treated as a proven 1.12 API rule. Chat sending exists in the source; external AI communication, real-time observation and server permission are separate unresolved problems.

A less autonomous version, in which an AI offers roleplay lines for me to send, remains a **possible direction only**. The separate roleplaying helper concept is not part of GuildChatBridge.

## Evidence

This creative account was supplied by me on October 31, 2026, after the original prototype. The repository proves that logging and a manual-send command were written; it does not prove that the imagined AI behavior was implemented, tested or approved for a server. See [the journal](docs/DEVLOG.md) and [architecture](docs/ARCHITECTURE.md).
