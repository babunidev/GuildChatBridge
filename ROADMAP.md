# GuildChatBridge — roadmap

**Status:** On ice. There is no approved feature schedule or active release milestone.

## Existing prototype — source observed, not runtime verified

- [x] Commit a Lua addon and 1.12-interface TOC.
- [x] Implement code paths for guild-message capture, roster-name storage and a manual `/gcai` send command.
- [ ] Verify successful loading and operation in the intended game client.
- [ ] Implement any actual external AI integration or generated response workflow.

The checked items describe committed source, not successful gameplay tests.

## Questions to resolve before reconsidering the project

- [ ] Identify the intended client, realm and current server rules on automated chat and external tools.
- [ ] Test the legacy client APIs, Lua 5.0 event conventions, `SendChatMessage` behavior and chat throttling in a controlled environment.
- [ ] Establish whether game events can reach a local AI promptly through a permitted interface. `SavedVariables` alone are not a continuous live bridge.
- [ ] Determine whether any return path for AI-generated text is technically supported and acceptable on that server.
- [ ] Define moderation, transparency, consent, character voice, rate limits and an immediate off switch.
- [ ] Fix or document prototype concerns: initialization after saved variables load, date formatting, roster refresh behavior, data retention and delivery reporting.

## Possible futures — not approved implementation

**Assisted roleplay:** An external local AI proposes short lines based on permitted observations; the player chooses whether to speak.

**Limited experimental autonomy:** A character occasionally speaks in guild or group chat, but only if the specific client capabilities, server policy and design safeguards allow it.

**Archive only:** Preserve the original idea and findings even if the desired interaction remains impractical.

No new code, test outcome or decision to restart development is implied by these possibilities.
