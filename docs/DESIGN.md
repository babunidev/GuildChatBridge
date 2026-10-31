# GuildChatBridge — experience design

**Project author and creative direction:** Babuni

The observable interaction separates capture from deliberate manual transmission. A possible future AI-assisted guild interface is a reconstruction from the name, manifest notes and source comment; it is not a delivered feature or recovered approval. The original README description, “a very secret guild chat project”, is preserved in the historical record below.

Printed copies may help a player inspect messages, but a source comment claiming they ensure `WoWChatLog.txt` output is not proof that client file logging is enabled. Roster snapshots contain names only, not ranks, membership history or a conversation model.

## Verification priorities

- Validate Lua syntax, addon varargs and callback argument conventions against the intended 1.12 client; interface 11200 alone does not establish compatibility.
- Check `%f` timestamp handling, saved-variable initialization timing and malformed existing DB tables.
- Check whether calling `GuildRoster()` inside its update event causes repeated requests/events.
- Verify guild membership and send failures; the command prints confirmation after requesting a send, without delivery acknowledgement.
- Decide retention and clearing behavior before extended use; storage grows without a bound and printed text does not ensure disk chat logging.
