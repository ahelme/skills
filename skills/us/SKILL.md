---
name: us
description: Update Slack — post a status update and read recent messages
user_invocable: true
arguments:
  - name: message
    description: Optional message to post (otherwise summarise recent work)
    required: false
---

1. Read recent Slack: `~/bin/team-hear`
2. Briefly acknowledge new messages from other teams
3. Post update: `~/bin/team-say "<message or auto-summary>"`
   - If no message given, summarise this session's work in one terse line
   - Your emoji/team/name is prepended automatically from `.claude/teams-chat.local.md`
