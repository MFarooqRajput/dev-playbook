# Git Rebase Commands

Rebase only when there are conflicts or in special cases

Switch to the `development` branch and update it

```zsh
git checkout development
git pull
```

Switch to your feature branch and rebase onto `development`

```zsh
git checkout feature
git rebase development
```

If conflicts arise, resolve them, then force-push the changes

```zsh
git push -f
git push --force origin feature
```

## Basic Rebase

Rebase current branch onto another branch:
```zsh
git rebase <target-branch>
```

## Interactive Rebase

Rebase last N commits interactively:
```zsh
git rebase -i HEAD~N
```

In the interactive editor:
- `pick`: keep commit as is
- `reword`: edit commit message
- `edit`: modify commit
- `squash`: combine with previous commit
- `drop`: remove commit

## Rebase with Conflicts

Resolve conflicts during rebase:
```zsh
# After conflict occurs
git add <resolved-files>
git rebase --continue

# Abort rebase if needed
git rebase --abort
```

## Rebase Onto Specific Commit

Rebase onto a specific commit:
```zsh
git rebase --onto <new-base> <old-base> <branch>
```
