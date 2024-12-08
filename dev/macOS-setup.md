# macOS Setup

## Step One:

- Install Xcode from app store and open it
- install command line tools and accept licence as below.

```zsh
xcode-select --install
sudo xcodebuild -license
```

## Step Two:

Install [Homebrew](https://brew.sh/)

## Step Three:

- Terminal exit on exit
- Dock Menubar
  - Minimize application into icon dock
  - Automatically hide and show the Dock
  - Automatically hide and show the Menu bar
- Finder
  - General
  - Sidebar

## Step Four:

```zsh
mkdir Codebase
mkdir Screenshots
mkdir Sites
mkdir Storage
```

```zsh
defaults write com.apple.screencapture location /Users/username/Screenshots
killall SystemUIServer
```

```zsh
defaults write com.apple.finder ShowPathbar -bool true
defaults write com.apple.finder ShowStatusBar -bool true
defaults write com.apple.dock static-only -bool true
killall Dock
```
