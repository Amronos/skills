# skills

My agent skills. This repo is cloned to `~/.agents/skills` by my [dotfiles](https://github.com/Amronos/.dotfiles), and `.skill-lock.json` is symlinked to `~/.agents/.skill-lock.json`, so `npx skills add` and `npx skills update -g` write straight into this checkout. Commit and push the result.

## Personal skills

| Skill | What it does |
| --- | --- |
| [improve-skill](improve-skill/SKILL.md) | Tightens a whole skill and prunes what the agent can discover or what goes stale with new tool versions. |
| [plan-comment-pruning](plan-comment-pruning/SKILL.md) | Finds useless code comments and plans which workarounds to refactor and which to delete. |
| [triage-bugfix-prs](triage-bugfix-prs/SKILL.md) | Closes stale bugfix PRs and reports the rest in plain English. |

## Installed with skills.sh

These are unmodified copies. `.skill-lock.json` records the exact source of each.

| Skill | Source | License |
| --- | --- | --- |
| create-verification-skill, maintain-verification-skill, no-comments, unslop | [cursor/plugins](https://github.com/cursor/plugins/tree/main/pstack) | MIT |
| find-skills | [vercel-labs/skills](https://github.com/vercel-labs/skills) | MIT |
| frontend-design | [anthropics/skills](https://github.com/anthropics/skills) | See [LICENSE.txt](frontend-design/LICENSE.txt) |
| grill-me, grilling, improve-codebase-architecture, writing-for-agents | [mattpocock/skills](https://github.com/mattpocock/skills) | MIT |
| install-anti-slop | [dmmulroy/anti-slop](https://github.com/dmmulroy/anti-slop) | MIT |
| trees | [pierrecomputer/pierre](https://github.com/pierrecomputer/pierre) | Apache-2.0 |
