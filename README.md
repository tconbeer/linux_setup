# Set up Linux using WSL2 in Windows

Download and install VS Code: https://code.visualstudio.com/download

## Install gh and clone this repo

```
winget install --id GitHub.cli
mkdir ~/open
gh auth login
gh auth setup-git
gh repo clone tconbeer/linux_setup ~/open/linux_setup
```

## Configure Powershell and Windows Terminal

In Powershell using Windows Terminal (from this directory):

```
cp ./Microsoft.PowerShell_profile.ps1 $PROFILE
cp ./.omp-theme.omp.json ~
winget install JanDeDobbeleer.OhMyPosh -s winget
```

As an Admin in Powershell:

```
oh-my-posh font install FiraCode Nerd Font

wsl --install
```

Press `ctrl+,` to open Windows Terminal settings.
- Startup: Default Profile: Ubuntu
- Rendering: Select 'Use the new text renderer ("AtlasEngine")'
- Profiles > Defaults > Appearance (scroll down) > Text > Font: FiraCode Nerd Font; Size: 12
- Profiles > Defaults > Appearance (scroll down) > Text Formatting > Intense: Bold font

If necessary, create a profile for Ubuntu/bash.

The rest of this file should be done in bash.

## update linux packages

```bash
sudo apt update && sudo apt upgrade
```

## intall homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## install pyenv build dependencies

```bash
sudo apt install make build-essential libssl-dev zlib1g-dev \
    libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
    libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
```

## use homebrew to install things

```bash
brew update
brew install gcc pyenv gh pipenv pipx oh-my-posh openssl
```

## clone this repo
```bash
mkdir ~/open
gh auth login
gh auth setup-git
gh repo clone tconbeer/linux_setup ~/open/linux_setup
```

## configure profiles

```bash
cd ~/open/linux_setup
cp ./.profile ~/.profile
cp ./.bashrc ~/.bashrc
cp ./.omp-theme.omp.json ~/.omp-theme.omp.json
```

## install python

```bash
pyenv install 3.11.4
pyenv global 3.11.4
```

## install poetry

```bash
pipx install poetry
```
