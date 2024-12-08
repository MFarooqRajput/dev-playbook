# Install NVM, NodeJS, Yarn via Homebrew on MacOS

## Part A: Install NVM and NodeJS

Install `nvm` via Homebrew

```zsh
brew install nvm
```

Create system directory for nvm

```zsh
mkdir ~/.nvm
```

Add following line to your profile. (`.profile` or `.zshrc` or `.zprofile`)

```zsh
echo 'export NVM_DIR=~/.nvm' >> ~/.zshrc
echo '[ -s "/usr/local/opt/nvm/nvm.sh" ] && \. "/usr/local/opt/nvm/nvm.sh"' >> ~/.zshrc  # This loads nvm
echo '[ -s "/usr/local/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/usr/local/opt/nvm/etc/bash_completion.d/nvm"' >> ~/.zshrc  # This loads nvm bash_completion


#old
echo 'source $(brew --prefix nvm)/nvm.sh' >> ~/.zshrc
```

Close and open your terminal again or run the following command once for reload your profile.

```zsh
source ~/.zshrc
```

Verify `nvm` is installed

```zsh
nvm --version
```

Check all avaliable version by this command

```zsh
nvm ls-remote
```

Install NodeJS (_Recommended to install LTS version._)

```zsh
nvm install --lts='Hydrogen'
```

Check installed NodeJS in your machine.

```zsh
nvm ls
```

Set global nodejs version to environment.

```zsh
nvm use default
```

You can check the currently active version of Node.js by running

```zsh
node -v
```

## Part B: Install Yarn

Install yarn https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable

### Install via npm

It is recommended to install Yarn through the npm package manager, which comes bundled with Node.js when you install it on your system.

Once you have npm installed you can run the following both to install and upgrade Yarn.

```zsh
npm install --global yarn
```
