# Creating a Global .gitignore on Unix/Linux/Mac S

Ever add directories or files to Git that you did not intend to track? If you are using a repository hosting service, such as GitHub, these files can be accessed by anyone in the world with an Internet connection!

Often, these files can have sensitive information - passwords, user data, etc. - or, on the other hand, can simply contain settings files created by the operating system (e.g. [.DS_Store](https://en.wikipedia.org/wiki/.DS_Store)) or text editor (e.g. [.idea](https://www.jetbrains.com/idea/help/project-and-ide-settings.html?search=.idea) in Webstorm) you are using.

Yes, you can create a `.gitignore` that is local to your repository and add the directories and folders that you do not want tracked by Git. This is definitely the best approach to take for files that are unique to that repository, such as the files containing sensitive information mentioned earlier.

On the other hand, for files such as .DS_Store, placing them in a global `.gitignore` might be appropriate so that they are excluded from Git in any subsequent repositories created.

Below are steps to take to create a global .gitignore using your computer's terminal.

# Gitignore Configuration

Check existing global gitignore:
```zsh
git config --get core.excludesfile
```

Create global gitignore file:
```zsh
touch ~/.gitignore
```

Configure global gitignore:
```zsh
git config --global core.excludesfile ~/.gitignore
```

Open global gitignore file:
```zsh
open ~/.gitignore
```

If the command in step 1 returned a file name different than `.gitignore`, open that file instead.

Finally, add the directories and files that you want to be in the global `.gitignore` and save the file.

The information found on GitHub to [create ignore files](https://help.github.com/articles/ignoring-files/) and suggested [global .gitignore configurations](https://github.com/github/gitignore/blob/main/Global/macOS.gitignore) are handy.
