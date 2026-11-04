---
name: improve-skill
description: Tighten a whole skill and prune what the agent can discover or what goes stale with new tool versions.
disable-model-invocation: true
---

# Improve skill

The user names a skill, and sometimes a PR that edits it. Work on the whole skill as it reads on the PR's head branch, including lines the PR never touched. The PR diff only tells you where the skill is.

## Steps

1. Check out the PR's head branch, or the default branch when there is no PR. Read every file in the skill folder.
2. Apply `$cleanup`, `$writing-for-agents`, and `$unslop` to the whole skill.
3. Prune over-documentation. Ask two questions of every line:
   - Is it a cache? Would the agent find this by running `--help`, reading the files, trying the command, or reading the tool's docs? Delete it.
   - Is it volatile? Will it likely change with the tool's next release or nightly, like flag names, menu paths, file-format fields, or defaults? Delete it, or replace it with the command that looks it up.

   Keep what the agent cannot find by looking: the user's preferences, the reason behind a choice, gotchas the tool's docs don't mention, and step order that matters. When in doubt, cut.
4. Reread the result as a fresh agent. Every branch the skill handled before still has a path, every link resolves, and the frontmatter parses.
5. Commit to the PR branch, or open a PR when there was none. Report what you cut, grouped as cache, volatile, and cleanup, plus borderline lines you kept and why.
