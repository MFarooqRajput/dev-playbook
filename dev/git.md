# GIT

## Delete all except master

To delete all branches in your Git repository except master, simply issue the following command

```zsh
git branch | grep -v "master" | xargs git branch -D
```

If you want to delete branches such as master-prod, master-test or master-ui, you can adjust the RegEx used by the grep as follows

```zsh
git branch | grep -v " master$" | xargs git branch -D
```

## Change commit message

```zsh
git commit --amend
```

## Set user name and email

```zsh
git config --global user.name "MFarooqRajput"
git config --global user.email "raja.muhammad.farooq@gmail.com"
```

## Unset user password

```zsh
git config --global --unset user.password
```

## Show all not pushed commits from all branches

```zsh
git log --branches --not --remotes
```
