# wm

A thin wrapper around [workmux](https://github.com/raine/workmux) that starts a worktree with a predefined, templated prompt.

```sh
wm review 123          # workmux add pr-123 --pr 123 -p "<prompts/review.md>"
wm review 123 -- -b    # extra options after -- go straight to `workmux add`
wm -n review 123       # dry run: print the command and rendered prompt
wm --help              # list available commands
```

## Install

Symlink the script somewhere on your `PATH`:

```sh
ln -s "$PWD/wm" ~/.local/bin/wm
```

### Shell completion

Completes command names (with descriptions in zsh) and flags. New prompts are picked up without reloading the shell.

```sh
# ~/.bashrc
eval "$(wm --completion bash)"

# ~/.zshrc (after compinit)
eval "$(wm --completion zsh)"
```

## Adding a command

Each file in `prompts/` is a command named after the file. `prompts/fix.md` becomes `wm fix`:

```markdown
---
description: Fix a GitHub issue
args: ISSUE
workmux: fix-{{ISSUE}}
---
Fix GitHub issue #{{ISSUE}}. ...
```

- `args` — space-separated positional argument names. Each is available as `{{NAME}}`.
- `workmux` — arguments passed to `workmux add` before the prompt (split on whitespace).
- `description` — shown in `wm --help`.

Everything after the frontmatter is the prompt. Unknown placeholders are rejected so typos don't reach the agent.

Set `WM_PROMPTS_DIR` to load prompts from a different directory.
