---
name: gi
description: Create a GitHub issue with project, milestone, team assignment, and team signature
user_invocable: true
---

# /gi — Create GitHub Issue

## Usage

`/gi <title or description>` — creates a well-formed issue from your description.

## Steps

1. **Draft the issue** from `$ARGUMENTS` or ask user if no args given
2. **Determine milestone** — ask if unclear. Current milestones: `1.0` (milestone desc), `2.0` (milestone desc), `3.0` (milestone desc)
3. **Read team identity** from `.claude/teams-chat.local.md` (emoji, name, team)
4. **Create the issue and add to project:**

```bash
url=$(gh issue create --repo gh-user/repo \
  --title "<title>" \
  --body "$(cat <<'EOF'
<issue body>

<emoji> <name> — <team>
EOF
)" \
  --milestone "<milestone>" \
  --label "<team-label>") \
  && gh project item-add 3 --owner "@me" --url "$url"
```

5. **Set Assigned Team in project** via GraphQL:

```bash
# Get the project item ID, then set Assigned Team field
# Get the project item ID — use items(last: 10) since newly added items appear at the end
item_id=$(gh api graphql -f query='{ user(login: "gh-user") { projectV2(number: 3) { items(last: 10) { nodes { id content { ... on Issue { number } } } } } } }' --jq ".data.user.projectV2.items.nodes[] | select(.content.number == <ISSUE_NUMBER>) | .id")

# Project ID: # (projectId)
# Field ID: # (fieldId)
# Options: project-team=#, project-team=#, project-team=#
gh api graphql -f query="mutation { updateProjectV2ItemFieldValue(input: { projectId: \"#", itemId: \"$item_id\", fieldId: \"#", value: { singleSelectOptionId: \"<team_option_id>\" } }) { projectV2Item { id } } }" --silent
```

6. **Return the issue URL**

## Team Labels → Project Field Options

| Team Label | Assigned Team Option ID |
|------------|------------------------|
| `team-label` | `#1` (Team Name) |
| `team-label` | `#2` (Team Name) |
| `team-label` | `#3` (Team Name) |
