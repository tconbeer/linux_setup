# update linux packages

```
sudo apt-get update
sudo apt-get upgrade
```

# intall homebrew

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

# install pyenv build dependencies

```
sudo apt-get update; sudo apt-get install make build-essential libssl-dev zlib1g-dev \
    libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
    libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
```

# use homebrew to install things

```
brew update
brew install gcc
brew install pyenv
brew install gh
```

# configure profiles

```
cp ./.profile ~/.profile
cp ./.bashrc ~/.bashrc
```
