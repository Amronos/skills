---
name: plan-comment-pruning
description: Find useless code comments in a repo and plan which workarounds to refactor and which to delete.
disable-model-invocation: true
---

# Plan comment pruning

Audit every code comment and lint suppression in the repo, then come back with a high-level plan. Edit nothing.

## Keep-list

A comment survives only when it is one of these:

- A legal or license header.
- Non-obvious behavior forced by something outside the repo that we cannot change: a dependency, platform, vendor, or protocol. Cite the issue or upstream link when there is one.
- A doc comment that defines a public API contract.
- A lint suppression whose rule is style-only or wrong for this line.

Everything else is a prune candidate, including explanations of surprises in our own code. Treat `IMPORTANT` or `do not remove` as leads: read the code they guard and check whether the claim still holds.

## Steps

1. Find every comment and suppression in tracked source files, skipping vendored and generated code.
2. Sort each one into a bucket:
   - Delete: the comment adds nothing, or the code is clear without it.
   - Refactor: the comment props up a workaround in our code. Name the symbol and the change that makes the comment unnecessary, such as a rename, an extracted function, a type, a removed dead path, or a root-cause fix.
   - Keep: it matches the keep-list. Say which entry.
3. Report one table per bucket, grouped by area. Each refactor row has the symbol, the workaround, the fix, and a rough size: small, medium, or large. Give deletes as counts per area with a few examples. End with the order you would do the refactors in and why.
