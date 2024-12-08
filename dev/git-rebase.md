# How to Rebase

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
