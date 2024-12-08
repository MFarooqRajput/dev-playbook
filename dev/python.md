# Setting up python environment in macOS using Homebrew, Pyenv, and Pipenv

Pyenv and Pipenv are necessary tools if you are working on different projects that need to be deployed to production and maintain a clean codebase.

We often have a problem when working on different projects in the local system

- we might need different python versions for different projects (less common) or
- we might need python packages compatible with particular versions (more likely).
- Virtual environments for different projects for easy deployments

## Installing Pyenv

We can install python using Homebrew with brew install python or for a specific version `brew install python@3.7`, but using Pyenv is a better way of handling different versions.

Install `pyenv` via Homebrew

```zsh
brew install pyenv
```

Add following line to your profile.

```zsh
echo '# Pyenv' >> ~/.zshrc
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc

echo 'if which pyenv > /dev/null; then eval "$(pyenv init --path)"; fi' >> ~/.zshrc
```

Close and open your terminal again or run one the following command once for reload your profile.

```zsh
source ~/.zshrc
```

Verify `pyenv` is installed

```zsh
pyenv --version
```

Check all avaliable version by this command

```zsh
pyenv install --list
```

To install a specific version

```zsh
pyenv install 3.9.21
```

By default, macOS picks the system python version. To set pyenv version as default.

```zsh
pyenv global 3.9.21
```

Check the python version and it should reflect the version set as global.

```zsh
python --version
python3 --version
```

If a particular project needs a different python version, then install that version first (if not installed already), navigate to the project folder, and set that version as local to that folder.

```zsh
pyenv install 3.6.5
cd <path to project folder>
pyenv local 3.6.5
```

To check all python versions installed using pyenv, enter this command

```zsh
pyenv versions
```

The which command is helpful for determining the full path to a system executable.

```zsh
which python3
pyenv which python3
which pip3
```

## Install Pipenv

You can install pipenv via Homebrew. Install pipenv

```zsh
brew install pipenv
```

verify installation

```zsh
pipenv --version
```

### Environment

Activate

```zsh
cd <path to project folder>
pipenv shell
```

Check version of Python

```zsh
python --version
```

Enter into Python and check path

```zsh
python
>>> import sys
>>> sys.executable
>>> quit()
```

Exiting the virtualenv

```zsh
exit
```

Install a package

```zsh
pipenv install <pkg>
```

Uninstall a package

```zsh
pipenv uninstall <pkg>
```

Check local packages

```zsh
pipenv lock -r
```

Install a dev package

```zsh
pipenv install <pkg> --dev
```

Install from requirements.txt

```zsh
pipenv install -r ./requirements.txt
```

Check security vulnerabilities

```zsh
pipenv check
```

Check dependency graph

```zsh
pipenv graph
```

Set lockfile - before deployment

```zsh
pipenv lock
```

Ignore pipfile

```zsh
pipenv install --ignore-pipfile
```

Run with pipenv

```zsh
pipenv run *
```

View the venv directory

```zsh
cd <path to project folder>
pipenv --venv
```

Detele the enviornment

```zsh
cd <path to project folder>
pipenv --rm
rm Pipfile*
```
