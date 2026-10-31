# GuildChatBridge — decisions and evidence

**Project author and creative direction:** Babuni

| Implemented choice | Evidence | Interpretation boundary |
| --- | --- | --- |
| Keep received text locally | `guildMessages` append and TOC SavedVariables | No retention policy or historical approval recovered |
| Send user-supplied text | `/gcai` handler | “AI responses” comment does not demonstrate AI generation |
| Refresh roster on event | `GUILD_ROSTER_UPDATE` handler | Re-entrant refresh risk remains untested |
| Print messages | `print` calls | Disk log creation is unverified |

## Open verification

- Validate Lua syntax, addon varargs and callback argument conventions against the intended 1.12 client; interface 11200 alone does not establish compatibility.
- Check `%f` timestamp handling, saved-variable initialization timing and malformed existing DB tables.
- Check whether calling `GuildRoster()` inside its update event causes repeated requests/events.
- Verify guild membership and send failures; the command prints confirmation after requesting a send, without delivery acknowledgement.
- Decide retention and clearing behavior before extended use; storage grows without a bound and printed text does not ensure disk chat logging.

These are source-observed choices and proposed checks, not invented historical approvals or an approved feature backlog.

## Preserved earlier documentation

The following earlier record is retained verbatim. Statements about unavailable history or pending verification describe that earlier snapshot; the dated evidence above supplements it.

# GuildChatBridge — design evidence and decisions

**Author:** Babuni

## Source-observed approach (not a recovered approval)

The current code performs message capture and transmission; no external language model call, AI generation, or working integration bridge is present in the inspected source.

## Open questions

- Whether the current code exactly matches the author's desired interaction on the target client is not independently verified.
- No previously rejected alternatives or historical approvals are claimed without direct records.

## 2026-10-31 — naming decision

I chose **GuildChatBridge** as the GitHub repository name to describe the current guild-chat bridge experiment without suggesting that it already generates AI replies. The installed addon still uses the historical `GuildChatAI` identifiers. This is a documentation and repository naming change, not a runtime migration.
