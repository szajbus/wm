---
description: Review a PR in a fresh worktree
args: PR
workmux: pr-{{PR}} --pr {{PR}}
---
Review PR {{PR}}.

Find gaps, possible improvements, deviations from established conventions. Demand high standards. Check for unintended side effects, code decoupling opportunities, unnecessary cyclomatic complexity, indirection and duplication. Remove comments that merely repeat what the code does.

First, explain what the PR does from business/product perspective, then list your findings breaking them into sections: Blockers, Important, Minor. Always use numbered lists.

Feel free to suggest substantial refactoring or change of approach if the solution doesn’t seem right. 
Suggest creating GitHub issues for follow-ups or unrelated changes.

If the PR breaks any explicit development guidelines or conventions for this project, suggest (as a follow-up) the way to strengthen those guidelines to prevent that from happening again. If you think a particular mistake justifies introducing new guidelines, suggest a follow-up as well.

Unless there is something very unusual to report, do not mention tests, type checks or linters you ran.

Focus on the review subject, do not comment on PR’s scope (number of commits, big diff, etc).

Make one commit per item.
