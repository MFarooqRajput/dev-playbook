# How to Tell What Shell Your Mac is Using

Every Mac comes with a Unix shell that provides a command line interface. Macs running macOS 10.15 and later use `zsh` by default. Before that, Macs used the `bash` shell by default. Of course, no matter what version of macOS you’re using, you can change the shell your Mac is using.

What shell is your Mac using? There’s an easy way to tell, here’s how.

1. Open the Terminal application on your Mac.
2. At the prompt, type `echo $0`, as shown below.

```zsh
echo $0
```

The name of the shell the Mac is using will be displayed in the output.

# How to Set Bash as the Default Shell on Mac

Every new Mac uses the `zsh` by default, but you can quickly and easily switch the default shell back to `bash`. There are several reasons you might want to do this. For example, you may need to be using the bash shell to execute bash scripts on a Mac.

Here’s how to set `bash` as the default shell on your Mac:

1. Open your Terminal application.
2. Type the following command and press Return:

```zsh
chsh -s /bin/bash
```

3. Enter your account password when prompted.

That’s it! Your Mac will now use `bash` as the default shell.

# Switching Back to Zsh as Default

If you want to stop using the `bash` shell, you can switch back to using `zsh` as the default shell.

Here’s how to set `zsh` as the default shell on your Mac:

1. Open your Terminal application.
2. Type the following command and press Return:

```zsh
chsh -s /bin/zsh
```

3. Enter your account password when prompted.

Your Mac will once again use `zsh` as the default shell.
