# Git Commands Reference

## Branch Management

Delete all branches except exact "master" branch (excludes master-prod, master-test, etc.):
```zsh
git branch | grep -v "master" | xargs git branch -D
```

Delete all branches except any branch containing "master" (includes master-prod, master-test, etc.):
```zsh
git branch | grep -v " master$" | xargs git branch -D
```

## Commit Management

Amend the last commit message:
```zsh
git commit --amend
```

View unpushed commits across all branches:
```zsh
git log --branches --not --remotes
```

## Git Configuration

Set global Git username:
```zsh
git config --global user.name "Your Name"
```

Set global Git email:
```zsh
git config --global user.email "your.email@example.com"
```

Remove stored Git password:
```zsh
git config --global --unset user.password
```
