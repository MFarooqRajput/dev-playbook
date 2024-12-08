# Creating a Global .gitignore on Unix/Linux/Mac S

Ever add directories or files to Git that you did not intend to track? If you are using a repository hosting service, such as GitHub, these files can be accessed by anyone in the world with an Internet connection!

Often, these files can have sensitive information - passwords, user data, etc. - or, on the other hand, can simply contain settings files created by the operating system (e.g. [.DS_Store](https://en.wikipedia.org/wiki/.DS_Store)) or text editor (e.g. [.idea](https://www.jetbrains.com/idea/help/project-and-ide-settings.html?search=.idea) in Webstorm) you are using.

Yes, you can create a `.gitignore` that is local to your repository and add the directories and folders that you do not want tracked by Git. This is definitely the best approach to take for files that are unique to that repository, such as the files containing sensitive information mentioned earlier.

On the other hand, for files such as .DS_Store, placing them in a global `.gitignore` might be appropriate so that they are excluded from Git in any subsequent repositories created.

Below are steps to take to create a global .gitignore using your computer's terminal.

1. Check whether a global .gitignore file exists.

```zsh
git config --get core.excludesfile
```

If the commands does not return anything, move to step 2. If the command returns a filename, skip to step 4.

2. Create a new file that will serve as a global .gitignore.

```zsh
touch ~/.gitignore
```

The name given to the global `.gitignore` file can differ from the one used in the example.

**Note:** `~` is shorthand for your home directory. In OS X, this is equivalent to `/Users/accountname`.

3. Set up Git's `core.excludesfile` configuration to use the global .gitignore file just created.

```zsh
git config --global core.excludesfile ~/.gitignore
```

4. Open the global .gitignore file.

```zsh
open ~/.gitignore
```

**Note:** If the command in step 1 returned a file name different than `.gitignore`, open that file instead.

5. Finally, add the directories and files that you want to be in the global .gitignore and save the file.

**Note:** The information found on GitHub to [create ignore files](https://help.github.com/articles/ignoring-files/) and suggested [global .gitignore configurations](https://github.com/github/gitignore/blob/main/Global/macOS.gitignore) are handy.
