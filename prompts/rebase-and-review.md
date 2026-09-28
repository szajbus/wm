---
description: Review a PR in a fresh worktree, rebased on local main, fix findings
args: PR
workmux: pr-{{PR}} --pr {{PR}}
---
Review PR {{PR}}.

Start by rebasing the PR’s branch on local main.

Find gaps, possible improvements, deviations from established conventions. Demand high standards. Check for unintended side effects, code decoupling opportunities, unnecessary cyclomatic complexity, indirection and duplication. Remove comments that merely repeat what the code does.

First, explain what the PR does from business/product perspective, then list your findings breaking them into sections: Blockers, Important, Minor, Decisions for you, Suggested follow-ups. Always use numbered lists.

Feel free to suggest substantial refactoring or change of approach if the solution doesn’t seem right. If you see obvious fixes to any of the findings, implement them straight away. Otherwise escalate by putting in “Decisions for you” section always providing recommendation or relevant context.

Suggest creating GitHub issues for follow-ups or unrelated changes, unless it makes sense to address them immediately.

If the PR breaks any explicit development guidelines or conventions for this project, suggest (as a follow-up) the way to strengthen those guidelines to prevent that from happening again. If you think a particular mistake justifies introducing new guidelines, suggest a follow-up as well.

Unless there is something very unusual to report, do not mention tests, type checks or linters you ran (I assume you run them and they passed), how the rebase went or that the branch needs to be force-pushed (that is clear because of the rebase).

Focus on the review subject, do not comment on PR’s scope (number of commits, big diff, etc).

Make one commit per item.
