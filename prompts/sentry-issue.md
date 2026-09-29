---
description: Investigate a Sentry issue in a fresh worktree branched off main, fix if clear
args: ID
workmux: sentry-{{ID}} --base main
---
Investigate Sentry issue {{ID}}.

Start by fetching the issue from Sentry: the stack trace, breadcrumbs, tags, affected releases and environments, frequency and first/last seen dates, and a few recent events to see what varies between them. Then explore the relevant code until you understand the root cause, not just where the exception surfaced.

Check git history around the first-seen date and the affected releases for changes that may have introduced it.

Determine which kind of problem this is: a bug in our code, bad input or data we should handle gracefully, a failure of an external dependency, or noise that should be filtered or downgraded rather than fixed.

If the investigation depends on context the issue doesn't include (e.g. the actual records, payloads, user or account state, configuration, or logs from other systems), don't guess: stop and ask me for it, saying exactly what you need, why, and how I can get it (e.g. a query to run). Clearly separate what you verified from what you inferred.

If the root cause is clear and the fix is straightforward, reproduce the problem with a failing test first where feasible, then fix it. If the root cause is uncertain, the fix is risky, or there are several reasonable approaches with meaningful trade-offs, stop and ask before implementing, always providing your recommendation. Follow established conventions of this project. Keep the change focused: no drive-by refactoring, but mention anything worth addressing separately as a suggested follow-up.

When done, explain to me the problem: what goes wrong, the root cause, and its impact on users from business/product perspective (who is affected, how often, what they experience). Then explain the fix: what it changes, why it addresses the root cause rather than the symptom, and how the behavior will differ for users. Then list anything that needs my attention in sections: Decisions for you, Suggested follow-ups. Always use numbered lists. If you could not pin down the root cause, say so plainly, list the hypotheses you ruled out and what additional data (logging, instrumentation) would settle it.

Suggest creating GitHub issues for follow-ups or unrelated problems you came across.

Unless there is something very unusual to report, do not mention tests, type checks or linters you ran (I assume you run them and they passed).

Make small, focused commits. Reference the Sentry issue in commit messages (e.g. "Fixes {{ID}}" in the final one).
