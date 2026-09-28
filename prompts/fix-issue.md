---
description: Fix a GitHub issue in a fresh worktree branched off main
args: ISSUE
workmux: issue-{{ISSUE}} --base main
---
Fix GitHub issue #{{ISSUE}}.

Start by reading the issue and its comments with `gh issue view {{ISSUE}} --comments`, then explore the relevant code until you understand the root cause, not just the symptom.

If the issue is ambiguous, the root cause points to a different problem than described, or there are several reasonable approaches with meaningful trade-offs, stop and ask before implementing, always providing your recommendation.

Reproduce the problem with a failing test first where feasible, then fix it. Follow established conventions of this project. Keep the change focused: no drive-by refactoring, but mention anything worth addressing separately as a suggested follow-up.

When done, explain the root cause and the fix from business/product perspective, then list anything that needs my attention in sections: Decisions for you, Suggested follow-ups. Always use numbered lists.

Suggest creating GitHub issues for follow-ups or unrelated problems you came across.

Unless there is something very unusual to report, do not mention tests, type checks or linters you ran (I assume you run them and they passed).

Make small, focused commits. Reference the issue in commit messages (e.g. "Fixes #{{ISSUE}}" in the final one).
