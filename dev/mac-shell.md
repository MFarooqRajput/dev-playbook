# macOS Shell Configuration Guide

Default Shell Configuration

- macOS 10.15 (Catalina) and later: `zsh` is the default shell
- Earlier versions: `bash` is the default shell

To determine your current shell:

```zsh
echo $0
```

## Shell Configuration

To configure `bash` as your default shell:

```zsh
chsh -s /bin/bash
```

To configure `zsh` as your default shell:

```zsh
chsh -s /bin/zsh
```

## Shell Customization

### Zsh Configuration

1. Create or edit `.zshrc` file:
```zsh
touch ~/.zshrc
```

2. Add custom configurations:
```zsh
# Enable color support
export CLICOLOR=1
export LSCOLORS=GxFxCxDxBxegedabagaced

# Set default editor
export EDITOR='nano'

# Add custom aliases
alias ll='ls -la'
alias ..='cd ..'
```

### Bash Configuration

1. Create or edit `.bash_profile`:
```zsh
touch ~/.bash_profile
```

2. Add custom configurations:
```zsh
# Enable color support
export CLICOLOR=1
export LSCOLORS=GxFxCxDxBxegedabagaced

# Set default editor
export EDITOR='nano'

# Add custom aliases
alias ll='ls -la'
alias ..='cd ..'
```