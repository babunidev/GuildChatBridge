# GuildChatBridge — decisions and unresolved questions

## Established human creative direction

**Original experiment (recounted 2026-10-31).** The idea was to let my player-controlled WoW character develop an independent conversational presence. Guild chat was the priority; relevant gameplay events and possibly party/raid chat could broaden their awareness. The player would still control movement and gameplay actions.

**Putting the experiment on ice (recounted 2026-10-31).** The attempted implementation did not deliver the autonomous conversation loop. Believing that chat output depended on direct user input, and unwilling to use unavailable or questionable interfaces, I paused the project instead of presenting a partial system as complete.

**Keeping the project (recounted 2026-10-31).** The repository remains available because the underlying roleplaying experiment still interests me. This does not authorize renewed development or choose a replacement design.

**Name change (2026-10-31).** The repository changed from `GuildChatAI` to `GuildChatBridge` to describe the present bridge experiment without implying that AI reply generation exists. Runtime identifiers remain unchanged.

## Source-observed implementation, not recovered design approvals

| Existing code | Evidence | Limitation |
| --- | --- | --- |
| Local guild-message capture | `CHAT_MSG_GUILD` and `guildMessages` | No live external stream |
| Stored roster names | `GUILD_ROSTER_UPDATE` and `guildRoster` | No rich guild relationship model |
| User-supplied guild chat send | `/gcai` and `SendChatMessage` | Not an AI response loop |
| Printed message copies | `print` call | Does not prove disk chat logging |

## Open technical and social questions

The original assumption about needing keyboard confirmation for **every** guild message is not confirmed by the available APIs and historical examples. This changes how the technical obstacle should be described, without changing the fact that the original project was paused. A functioning local-AI exchange, verified 1.12 compatibility, specific server rules, and acceptable player-facing behavior remain open.

Possible directions include an AI that **suggests** messages for manual selection or a tightly controlled autonomous voice, if allowed. Neither is currently an adopted implementation plan. The separate speech-based roleplaying-helper project should retain its own scope.

## Attribution and evidence

These creative decisions were supplied directly by the human creative on 2026-10-31; their original dates are not independently established. The code-based observations come from the existing repository. AI assistance analyzed and documented the distinction; it did not originate the original idea or decide to restart the project.
