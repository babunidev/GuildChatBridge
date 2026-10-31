# GuildChatBridge — intended experience

## The imagined interaction

During ordinary gameplay, I would continue making the decisions that move my character through the world. Their voice, however, might develop its own small life. Guildmates could be chatting while the character noticed something relevant, formed an opinion and occasionally joined the conversation in character.

Crafting, combat and loot were examples of context the AI might use, not features already captured by the addon. Guild chat was the main setting; party and raid channels were possible expansions.

The distinction from a traditional chatbot is important: the character would not simply answer every incoming message. Context, personality and selective interest were central to the intended illusion.

## What the current addon feels like

The code does something much smaller. It collects guild-message text and names, prints captured messages and offers `/gcai` to send text typed by the player. There is no character voice, contextual awareness, UI for proposed dialogue, or AI interaction. This interaction has not been tested in the intended game client during the documentation review.

## Boundaries for any redesign

The most interesting design challenge is also the social risk. An autonomous roleplayed character should not bury guild conversations, confuse people about who is speaking or continue when the player wants silence.

Ideas worth investigating, **not approved features**, include clear disclosure, channel selection, conservative response frequency, a prominent off control and a manual suggestion mode. Automatic publishing must be considered separately from generating interesting text. Technical feasibility alone would not settle whether the result belongs in a shared game.

This project concerns the character speaking in guild and group life; a separate roleplaying speech assistant is not a replacement for this concept.
