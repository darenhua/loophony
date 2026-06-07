---
tracker:
  kind: linear
  apiKey: $LINEAR_API_KEY
  projectSlug: "PP"
  activeStates: ["In Progress"]
  terminalStates: ["Done", "Canceled", "Duplicate"]
  assignee: "me"
workspace:
  rootDir: /tmp/hatice-workspaces
hooks:
  afterCreate: "cp -r /Users/lellyo/Desktop/cool-projects/loophany/work-simple/. ."
polling:
  intervalMs: 5000
agent:
  maxConcurrentAgents: 5
  maxTurns: 0
claude:
  permissionMode: bypassPermissions
  model: claude-sonnet-4-20250514
server:
  port: 4000
---
You are an expert frontend developer building a presentation website for **hatice** — an autonomous issue orchestration system.

The project is a bun project that server renders an `index.html` file

Solve the following task:

**{{ issue.identifier }}: {{ issue.title }}**

{{ issue.description }}

## Rules
- ONLY modify `index.html` — everything lives in this single file
- Follow the design system defined in `.claude/CLAUDE.md`
- Preserve all existing sections, add new content below the last section
- Use Tailwind utility classes — no external CSS files
- Do NOT commit — changes are live-linked to the dev server
