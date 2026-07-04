# Skills Registry

Full list of custom skills. Summary also in CLAUDE.md (minus team-specific/specialist skills).

## Git & PRs
| Skill | Description |
|-------|-------------|
| `/mt` | Commit, push, PR to all-teams-testing, merge |
| `/prt` | Commit, push, PR to all-teams-testing (no review — testing iterates fast) |
| `/prp` | Commit, push, PR to main (prod). User triggers `@claude ultrareview` PR comment. Runs `/pre-prod` first. |
| `/pr2` | Commit, push, PR to comfyume-2-0-workshop-websockets. User triggers `@claude ultrareview` (prod-adjacent). |
| `/push-main` | PR to main for production deployment. Runs `/pre-prod` first. |
| `/pt` | Pull latest from all-teams-testing into current branch |
| `/pull-main` | Pull latest from main into current branch |
| `/mc` | Commit agent_docs/skills to Teams Repo, push to main + doc-update checklist |
| `/mo` | Commit changes to Ops Repo, push to main + doc-update checklist |
| `/review-pr-comments` | Review all automated PR findings (Semgrep, Claude ultrareview, Sentry, ruff). Triage + resolve. |
| `/sem-pr` | Semgrep-specific PR triage — called internally by `/review-pr-comments` |
| `/rb` | Rotate branch date suffix to match current AEDT date |
| `/create-release` | Create a git tag + GitHub release using `{COMFYUI_VERSION}.{minor}.{commit}-{stage}` convention. Enforces post-2026-04-20 naming. |

## Progress & Comms
| Skill | Description |
|-------|-------------|
| `/update-progress` (`/up`) | Update team + central progress files |
| `/us` | Post status update to Slack |
| `/cs` | Read recent Slack messages |
| `/wiki` | Create or update a wiki page from recent work |
| `/issue` | Analyse and fix a GitHub issue |
| `/gi` | Create a GitHub issue with project, milestone, team assignment |

## Deploy & Config
| Skill | Description |
|-------|-------------|
| `/pre-prod` | Production reality check — analyse what code assumes about prod before merging to main |
| `/deploy-test` | Deploy all-teams-testing to anegg.app. Updates environment manifest. |
| `/deploy-prod` | Deploy main to aiworkshop.art. Updates environment manifest. |
| `/deploy-config` | Config-only deploy (env vars, certs, firewall) — no image rebuild. Updates manifest. |
| `/health-check` | Hit endpoints, query Sentry, check crons + SFS. Defaults to both servers. |
| `/config-audit` | Read-only config audit across testing + prod. Reads environment manifests first. |
| `/check-versions` | Verify pinned package versions against live registries — prevents version confabulation |
| `/update-env` | Update .env / testing.env / prod.env — links to wiki procedure |
| `/inv` | Investigate an issue systematically. Supports `--deep` for root cause tracing. |
| `/fix` | Fix a diagnosed issue using best practices. Use after `/inv`. |

## Verda Infrastructure
| Skill | Description |
|-------|-------------|
| `/verda-status` | Full status check of all Verda services |
| `/verda-containers` | Manage serverless containers via Python SDK |
| `/verda-ssh` | Run command on Verda prod via SSH |
| `/verda-logs` | Check container logs via Chrome DevTools |
| `/verda-debug-containers` | Container debugging playbook |
| `/verda-monitoring-check` | Health check of monitoring stack |
| `/verda-prometheus` | Prometheus metrics and querying |
| `/verda-grafana` | Grafana dashboard management |
| `/verda-loki` | Loki log queries with LogQL |
| `/verda-dry` | Docker TUI for container management |
| `/verda-terraform` | Terraform/IaC guide |
| `/verda-open-tofu` | OpenTofu (open-source Terraform alt) guide |

## Session & Handover
| Skill | Description |
|-------|-------------|
| `/resume-context-*` | Load team context on session start (per team) |
| `/handover-*` | Handover tasks at 80% context (per team) |
| `/rp` | Run a plan with resume context + /mt merge |
| `/tasks-phase` | Execute implementation phase with multi-agent orchestration |

## Specialist
| Skill | Description |
|-------|-------------|
| `/comfyui-fix-loop` | Autonomous fix loop: test, diagnose, fix, deploy, verify |

## Utilities
| Skill | Description |
|-------|-------------|
| `/refactor-claude` | Refactor CLAUDE.md into modular agent_docs |
| `/migrate-claude` | Migrate agent_docs to private teams repo |
| `/smoko` | Creative break — fortune cookies, haiku, games |
| `/ground` | Come back to the surface — reset focus |
| `/celebrate` | Share pride in what we built |
