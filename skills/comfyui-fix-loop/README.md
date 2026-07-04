# README for comfyui-fix-loop

# Requirements (alter as needed)

- Git (see branch config below)
- Dockerised project
- ComfyUI
- ChromeDevTools / Chromium
- GPU queue
- Configuration files as listed below
- Deploy script or other deployment instructions

# Configuration

1. Set CONTEXT MANAGEMENT, SCOPE, LOOP PROTOCOL within SKILL.md
2. Set git branch (e.g. `ralph-loop`)
2. Set up these required files:
	.claude/skills/ralph-loop/SKILL.md
	.claude/qa-state.json
	CLAUDE.md
	 ./scripts/deploy.sh
	 .claude/skills/resume-context-ralph-loop/context.md
	
Note: can be adapted to improve or fix whatever is required - not comfyui specific.