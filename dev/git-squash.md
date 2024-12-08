# Git Squash Commands

## Squash Last N Commits

Squash the last 3 commits into one:
```zsh
git rebase -i HEAD~3
```

In the interactive rebase editor:
1. Keep first commit as `pick`
2. Change other commits to `squash` or `s`
3. Save and exit editor (`:wq`)
4. Edit final commit message in the next editor

## View Commit History

Display commit history in one line:
```zsh
git log --oneline
```

## Squash During Merge

Squash commits when merging a branch:
```zsh
git merge --squash feature-branch
git commit -m "Squashed feature branch commits"
```

## Squash All Commits in Branch

Squash all commits in current branch:
```zsh
git reset --soft HEAD~$(git rev-list --count HEAD ^master)
git commit -m "Squashed all commits"
```
