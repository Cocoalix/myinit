# Neovim installation-guide

## 1. get python3

### Windows

1. get from [official](https://www.python.org/)

1. exec this
  ```bash
  pip install pynvim
  ```

### Mac

1. exec this

```zsh
brew install pyenv
brew install pyenv-virtualenv
```

1. write `.zprofile`

```.zprofile
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

1. exec this

```zsh
# check installable python version
pyenv install --list
# check installed python version
pyenv versions

# create python2 env (choose newer version)
pyenv install 2.7.15
pyenv virtualenv 2.7.15 neovim2
pyenv activate neovim2
pip2 install neovim
pyenv which python

# create python3 env (choose newer version)
pyenv install 3.5.3
pyenv virtualenv 3.5.3 neovim3
pyenv activate neovim3
pip install neovim
pyenv which python
```

## 2. get neovim

### Windows

get from [official](https://github.com/neovim/neovim/releases)

### Mac

```zsh
brew install neovim
```

## 3. attach my init.vim

### Windows

```bash
mkdir -p ~/AppData/Local/nvim
cp ./init.vim ~/AppData/Local/nvim/init.vim
cp ./*.vim ~/AppData/Local/nvim/
```

### Mac

```zsh
mkdir -p ~/.config/nvim
cp ./init.vim ~/.config/nvim/init.vim
cp ./*.vim ~/.config/nvim/
```

## 4. REPLACE g:python3_host_prog

1. exec `:checkhealth` on nvim

1. copy `INFO: Executable:` row in  `Python 3 provider`

1. paste to `g:python3_host_prog`

1. exec `:echo has('python3')` on nvim for check useable python3

## 5. exec nvim

1. auto install dein and plugins
