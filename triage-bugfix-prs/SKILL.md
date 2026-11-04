---
name: triage-bugfix-prs
description: Close stale bugfix PRs and report the status of the rest in plain English.
disable-model-invocation: true
---

# Triage bugfix PRs

The group is the open PRs the user names, by default those matching `sprocket-bugfix` by label or branch prefix.

## Steps

1. List every PR in the group with its description, linked issues, checks, reviews, and merge state.
2. Decide whether each PR is still relevant. A PR is stale when one of these holds:
   - the default branch already fixes the bug, through another PR or a rewrite;
   - the code it changes no longer exists;
   - another open PR in the group duplicates or supersedes it.

   Prove each stale verdict with the commit, PR, or file on the current default branch that shows it. A PR you cannot prove stale stays open.
3. Close each stale PR with a comment that gives the reason and links the proof.
4. For each PR still open, find what blocks the merge: failing checks, conflicts, missing or requested-changes reviews, an unanswered question in the thread, or draft state. Write "nothing" when it is ready.
5. Report a table of the open PRs:

   | PR | Status | Why it isn't merged | What it does |
   | --- | --- | --- | --- |

   "What it does" is one or two sentences a non-developer could follow: the bug a user sees, and what changes for them after the fix. Below the table, list the PRs you closed with the reason, so the user can reopen any you got wrong.
