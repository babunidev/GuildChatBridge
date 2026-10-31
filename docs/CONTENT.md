# GuildChatBridge — content and character voice

## Existing content

The repository supplies only short utility strings: a load message, `/gcai` usage and send confirmation, and a `[Guild]` message prefix. Captured guild text and player names come from other players, not a bundled character script. The code uses `%m/%d %H:%M:%S.%f` as a timestamp format; support for `%f` remains unverified.

No artwork, character profile, dialogue prompts, local model, generated messages or story corpus is present.

## Intended content, not implemented

The original idea depended on the character expressing their own perspective. A remembered guild discussion, a recent fight, a crafted item or found loot might have supplied context for a short in-character response. That voice was meant to feel like part of a roleplayed character's life, not a generic chatbot replying to every line.

The creative direction is established; the character's precise personality, prompting rules, event filtering and dialogue style are **not** specified or approved in this repository.

## Social and data considerations

Guild conversations and roster names are other people's content. Any future logging or local-AI processing would need clear scope, reasonable retention, disclosure of AI participation and controls that prevent unsolicited repetitive messages. Existing storage has no deletion interface or retention limit.
