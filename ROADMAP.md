# GuildChatBridge — roadmap

**Project author and creative direction:** Babuni

## Current implementation

A guild-chat capture and manual-send experiment for WoW. It stores received guild messages and roster names, and `/gcai <message>` forwards supplied text to guild chat. There is no demonstrated real AI integration: no model request, response generation, external bridge, credentials, or automatic reply loop exists in the inspected source.

## Proposed verification work

- [ ] Validate Lua syntax, addon varargs and callback argument conventions against the intended 1.12 client; interface 11200 alone does not establish compatibility.
- [ ] Check `%f` timestamp handling, saved-variable initialization timing and malformed existing DB tables.
- [ ] Check whether calling `GuildRoster()` inside its update event causes repeated requests/events.
- [ ] Verify guild membership and send failures; the command prints confirmation after requesting a send, without delivery acknowledgement.
- [ ] Decide retention and clearing behavior before extended use; storage grows without a bound and printed text does not ensure disk chat logging.

No new gameplay feature or release is approved by this documentation pass. Resolve compatibility findings in a separately scoped implementation change and update this record with actual test results.

## Preserved earlier documentation

The following earlier record is retained verbatim. Statements about unavailable history or pending verification describe that earlier snapshot; the dated evidence above supplements it.

# GuildChatBridge — roadmap

**Author:** Babuni

## Current snapshot

The code and manifest are present on the default branch; this review did not execute the addon. No release or historical feature milestone is inferred from the repository snapshot.

## Verification work (proposed; not approved feature changes)

Test against the declared WoW client version; inspect API and Lua syntax compatibility, timestamp formatting and guild-roster event behavior; do not claim that an AI bot is implemented.

## Future features

None approved or established by this documentation pass. Record new ideas separately before implementation.
