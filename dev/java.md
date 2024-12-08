# How to Manage Multiple Java Versions in MacOS

To install `jenv` and manage multiple versions of Java on macOS using Homebrew, follow these

## Installing Java Version Manager - jenv

We are going to make use of `brew` to install the `jenv`. To do that run following command to your terminal

```zsh
brew install jenv
```

Once you installed `jenv` into the machine successfully, next you need to add the following to your shells configuration file. Based on the shell you use you need to paste them in the correct file.

- For `bash` that would typically be `~/.bash_profile` or `~/.bashrc`
- For `zsh` it's `~/.zshrc` or `~/.zprofile`
- `~/.profile` if no `~/.bash_profile` or `~/.zprofile`

```zsh
	export PATH="$HOME/.jenv/bin:$PATH"
	eval "$(jenv init -)"
```

In order to paste these lines in your shell configuration file either you can use your text editor (i.e vim, nano, etc) or you can echo as follows to your shell configuration file. You should change the shell configuration file name based on the shell type you use.

```zsh
echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(jenv init -)"' >> ~/.zshrc
```

Once you are done with above steps restart your terminal application or resource your configuration. To do that you can use the following command (make sure to change the file name based on your shell type):

```zsh
source ~/.zshrc
```

You should now be able to run `jenv doctor` in terminal to verify your installation of `jenv`

```zsh
jenv doctor
```

Ignore all the errors and warnings that you see, if you are seeing `Jenv is correctly loaded` message on your terminal all good for now.

But there are a couple of more things you want to do before going to the next step, that’s Run the following commands in the terminal if you are using maven(i.e mvn):

```zsh
# ensure that JAVA_HOME is correct
jenv enable-plugin export

# make Maven aware of the Java version in use (and switch when your project does)
jenv enable-plugin maven
```

All good! Now we are fully configured to use `jenv` on our mac, What’s remaining is to install different JDK versions that we wish to switch between. In the next section, we shall look into it.

## Installing different JDK versions

There are two main flavors of JDK versions, Here I’m going to make use of Open JDK as it’s free and open source. For Java versions we need to specify the version with Homebrew which version to install, let’s install a couple of them. I’ll be using `openjdk`.

```zsh
brew install openjdk@11 openjdk@17

# or you can install a single version as follows:
brew install openjdk@21
```

## Configuring JDK Versions with jEnv

Now you are at the final step of configuring all the installed JDK versions with `jenv` in order to switch between different Java versions. We basically need to tell `jenv` where are the JDK versions we want it to manage, that’s what we are going to do in this section.

For the system Java wrappers to find this JDK, symlink it with

```zsh
sudo ln -sfn /usr/local/opt/openjdk@11/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-11.jdk
sudo ln -sfn /usr/local/opt/openjdk@17/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-17.jdk
```

To do that we need to find all of our JDK root paths. You can hit the following command in the command line to see all the installed JDK versions in your machine.

```zsh
/usr/libexec/java_home -V
```

It will list all of your installed JDK versions.

Now you can add to `jenv` each of the JDK you installed by the following command:

```zsh
#jenv add <your_jdk_path>
jenv add /usr/local/Cellar/openjdk@11/11.0.25/libexec/openjdk.jdk/Contents/Home
jenv add /usr/local/Cellar/openjdk@17/17.0.13/libexec/openjdk.jdk/Contents/Home
```

Now you can add each of the listed JDKs using the above command to `jenv`. Once you add all the JDKs to `jenv` you can list and see whether all the versions you add are available in the `jenv` using the following command.

```zsh
jenv versions
```

To set system-wide Java version

```zsh
jenv global 17
```

If a specific project needs a different version of Java just hit the following command in the terminal by standing in the directory of that project. `jenv` will then create a .java-version file that describes which JDK to use for. This file can safely be checked in so that your whole team runs the same version of Java (if using `jenv` of course).

```zsh
jenv local 11
```

If you need to run a different version of Java in your shell(i.e terminal window), you can run the following command.

```zsh
jenv shell openjdk64-17.0.13
```

To check current Java Version

```zsh
java -version
```
