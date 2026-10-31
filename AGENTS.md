# Development and documentation rules — GuildChatBridge

**Human creative and project author:** Babuni

## Authorship and narrative

- Write public-facing project history from the human creative's first-person perspective, with natural references to `I` and `my` **inside** sentences. Never begin a sentence with `I` or `My`.
- Describe what prompted the idea, what the creative decided and requested, what AI actually contributed, what changed, and what remains uncertain. Do not tell the creative's story in third person.
- Use **creative**, never **creator**, as the role label for a person who conceives or makes a work.
- Distinguish original human direction from AI suggestions, drafting, coding and repository operations. Do not present AI-authored code as hand-written by the creative.
- Prefer brief, readable development-journal entries over procedural reports. Preserve genuine disagreement or abandoned approaches when they explain the outcome.
- Retrospective reconstruction must be labeled. Do not invent motives, approvals, conversations, tests, commit dates or deployed features.

## Technical boundaries

- This is a **paused prototype**, not an operational AI bot. Never present autonomous chat or a local AI bridge as implemented.
- Do not state that `SendChatMessage` categorically requires manual keyboard input for guild chat. Confirm API behavior against the actual client and server; separate technical possibility from server permission.
- Never propose bypassing server safeguards, simulating prohibited input or secretly impersonating other players as the implementation strategy.
- Preserve the difference between the repository name `GuildChatBridge` and the historical installed-addon identifiers (`GuildChatAI.lua`, `GuildChatAI.toc`, `GuildChatAIDB` and `/gcai`).
- Read source and commit history before edits. A manifest label or source comment is not proof of a successful in-game run. Verify Lua 5.0 compatibility and the specific target client before making compatibility claims.
- Keep real source, existing features, possible futures and independently verified behavior clearly separated.

## Documentation workflow

- Maintain `README.md` (overview), `CONCEPT.md` (creative vision), `ROADMAP.md` (status/questions), `CHANGELOG.md` (actual changes), `docs/DEVLOG.md` (first-person history), `docs/DECISIONS.md` (choices and alternatives), `docs/DESIGN.md` (interaction), `docs/ARCHITECTURE.md` (technical facts), `docs/CONTENT.md` (text/content), and `docs/AI_COLLABORATION.md` (attribution).
- For substantial implementation, update affected documents alongside code and report exact tests and outcomes. For documentation-only work, do not quietly change addon behavior.
- Preserve original history through Git and the archival `docs/HISTORICAL_README.md`. Avoid nesting entire previous document versions inside current documents.
- Check relative links, cross-file contradictions and the exact commit after changes. Preserve existing license and third-party notices; do not infer license policy changes from discussion.
