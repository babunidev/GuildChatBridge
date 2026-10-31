# Development rules — GuildChatBridge

**By:** Babuni

Keep existing gameplay and player-facing behavior unless Babuni directs a change. Separate original author direction from AI analysis, edits and later reconstruction. Never infer past approvals from code or comments. Treat source as evidence of implementation, not proof of runtime behavior. When implementing, update README, CONCEPT, ROADMAP, CHANGELOG and docs/DEVLOG together. Preserve license terms, third-party attribution and prior dates. Test on the declared WoW client before calling a feature verified.

## Evidence and maintenance rules

- Read the actual branch, Lua, TOC, README and relevant dated diffs before editing. Keep source behavior, proposals and tested results separate.
- Preserve Babuni as project author; identify AI drafting, analysis or code assistance separately. Preserve historical records, aliases, license terms and third-party credit.
- Never treat a comment, version label or manifest interface as proof of runtime compatibility. Never claim tests were run without recording the command, environment and outcome.
- For material changes update README, CONCEPT, ROADMAP, CHANGELOG and docs/DEVLOG, plus architecture/design/content where affected. Link evidence and retain uncertainty.
- Documentation-only work must not change Lua, TOC, tests or assets. Check the diff and all relative documentation links before publishing.

## Repository-specific constraints

- Validate Lua syntax, addon varargs and callback argument conventions against the intended 1.12 client; interface 11200 alone does not establish compatibility.
- Check `%f` timestamp handling, saved-variable initialization timing and malformed existing DB tables.
- Check whether calling `GuildRoster()` inside its update event causes repeated requests/events.
- Verify guild membership and send failures; the command prints confirmation after requesting a send, without delivery acknowledgement.
- Decide retention and clearing behavior before extended use; storage grows without a bound and printed text does not ensure disk chat logging.

## Naming and narrative perspective

The current repository is `GuildChatBridge`; `GuildChatAI` remains the historical and installed-addon identifier. Never rename Lua/TOC files, SavedVariables or slash commands as a side effect of a documentation rename. Public project narratives are written from Babuni's first-person perspective (using `I` and `my`, without beginning sentences with `I` or `My`). AI contributions are described as assistance requested or directed by Babuni, without claiming unverified original design history. Neutral technical reference language is appropriate for code and verification tables. Preserve historical source snapshots as historical material.
