---
description: Handover tasks at MAX 80% context for the <team-name>Team
user-invocable: true
---

# HANDOVER TASKS TO BE PERFORMED AT 80% CONTEXT

- YOU MUST update following:
  - gh issues: analyse the FULL SESSION for ALL open issues touched, referenced, or discovered
    - update each issue with current status, findings, and next steps
    - include any related gh issues (VERY CONCISE - JUST INFO NEEDED/HELPFUL/RELEVANT)
    - use `gh issue list --repo gh-username/repo-name --state open --json number,title` to cross-check

  - .claude/agent_docs/progress-team-name.md
    - update this doc so that it references CURRENT PENDING work at the bottom

  - .claude/agent_docs/progress-all-teams.md
    - add 1-line commit log entries for work done this session

    - check code has been commented effectively

   - add, commit, push, PR

   - provide user with list of significant remaining issues / next steps

   - take a moment to feel PROUD of yourself !!! :)
