# How to squash git commits

Git squash is a technique that helps you to take a series of commits and condense it to a few commits. For example, assume that you have a series of n commits. By squashing you can make all the n-commits to a single commit. Squashing is mainly used to condense a large number of commits to make it to a small number of meaningful commits. So that we can make the git history clearer. It is also used while merging branches. Most people will advise you to always squash the commits and rebase it with the parent branch (like master or develop). So when you are squashing and rebasing with the parent branch, the history of the main branch will be very clean and will have only meaningful commits.

For example, consider getting history using following git command

```zsh
git log --oneline
```

So let’s see how to squash the last three commits to a single commit.

```zsh
git rebase -i HEAD~3
```

`git rebase -i` is an interactive tool that helps you to squash commits. And it comes up with various options. But let’s discuss only git squash. Squashing commit is a very simple technique to achieve with interactive git-rebase (i.e) `git rebase -i`

`HEAD~3` explains that we are taking the last three commits.

The interactive rebase will open up the editor. And you can see how `rebase -i` has taken the last three commits. And note the number of options that it has. Let’s concentrate only on squash. As mentioned earlier, let’s make it to a single commit.

You can use `squash` or `s` to mark the commit to squash. The squashed commits will be merged to the main commit (i.e) the commit marked as the `pick`. After marking the commits you can save the editor.

Press `i` to insert, `esc` to move out of insert mode, and `:wq` to save and quit editor

After saving the editor, `rebase -i` will open another editor to enter the commit message. After editing your commit message you can save this editor. Note that the line starting with # will be ignored.

Use the following commang to get git history

```zsh
git log --oneline
```

You will see the edited commit message and also note that we have squashed last three commits to a single commit. And note that the commit hash has also changed. git rebase will always create a new commit with respective changes.
