# macOS Development Environment Setup Guide

## 1. Xcode Installation
- Install Xcode from the App Store
- Install Command Line Tools and accept the license agreement:
```zsh
xcode-select --install
sudo xcodebuild -license accept
```

## 2. Homebrew Package Manager
Install [Homebrew](https://brew.sh/), the missing package manager for macOS:
```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Package Management

```zsh
brew search <package>
brew info <package>
brew install <package>
brew uninstall <package>
brew reinstall <package>
brew deps <package>


brew install --cask <app>
brew uninstall --cask <app>

brew list
brew list --cask

brew upgrade
```

System Maintenance

```zsh
brew doctor
brew update
brew cleanup
```

## 3. System Preferences Optimization

### Terminal & Shell
- Enable "Close if the shell exited cleanly" in Terminal preferences
- Set up your preferred shell (zsh, bash, etc.)

### Dock & Menu Bar
- Enable "Minimize windows into application icon"
- Enable "Automatically hide and show the Dock"
- Enable "Automatically hide and show the Menu bar"

### Finder Settings
- General
- Sidebar


### 4. Directory Structure Setup

Create essential directories for development:
```zsh
mkdir -p ~/Codebase
mkdir -p ~/Screenshots
mkdir -p ~/Sites
mkdir -p ~/Storage
```

Configure screenshot location:
```zsh
defaults write com.apple.screencapture location ~/Screenshots
killall SystemUIServer
```

Show path bar and status bar
```zsh
defaults write com.apple.finder ShowPathbar -bool true
defaults write com.apple.finder ShowStatusBar -bool true
defaults write com.apple.dock static-only -bool true
killall Dock
```
