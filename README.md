# Setup a New Machine!

Download, compile and install commonly used software to a custom path.

## Environment
- macOS Catalina 10.15.6 (19G73)
- MacBook Pro (13-inch, 2018, Four Thunderbolt 3 Ports)
- Processor 2.3 GHz Quad-Core Intel Core i5
- Memory 16 GB 2133 MHz LPDDR3
- Graphics Intel Iris Plus Graphics 655 1536 MB
```bash
Darwin 19.6.0 Darwin Kernel Version 19.6.0: Sun Jul  5 00:43:10 PDT 2020; root:xnu-6153.141.1~9/RELEASE_X86_64 x86_64
```

## Term of Usage

## Usage
```bash
# configure setup path, you can put them into your `.bashrc` or `.zshrc`
# e.g. install git

# Install oh my zsh, Oh My Zsh is an open source, community-driven framework for managing your zsh configuration.
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
# Install Vundle, Vundle is short for Vim bundle and is a Vim plugin manager.
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
vim +PluginInstall +qall
# Update config.
git clone https://github.com/YinminZhang/setup.git
cp vimrc ~/.vimrc && cp zshrc ~/.zshrc
source ~/.zshrc
```
## Table of Contents
1. [iTerm2](#iTerm2)
2. [zsh](#zsh)
3. [vim](#vim)
4. [tmux](#tmux)

### iTerm2
#### Font
After font config, the iTerm2 can display many icons.

First, we download fonts package.
```bash
brew tap homebrew/cask-fonts
brew cask install font-hack-nerd-font
```
Then, we config the font in iTerm2.

Preferences -> Profiles -> Open Profiles -> Edit Profiles -> Text
<img src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/e841ebe6-ed1f-45d0-b996-68096371a943/font.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210626%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210626T081511Z&X-Amz-Expires=86400&X-Amz-Signature=13ba9619e8fe28a7dd7162bd6f55011a09f7e0ec24dfe73042ac5987da43fd2b&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22font.png%22"></img>

#### Transparancy & Background
We can set image as iTerm2 background.

Preferences -> Profiles -> Open Profiles -> Edit Profiles -> Window
<img src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/afe6d4dc-fd4a-4d92-a251-0dc5962b6973/background.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210626%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210626T082413Z&X-Amz-Expires=86400&X-Amz-Signature=07a45529fb0af75e0a6e10d1d5dfc5ef0e1a9a3c331eaaf9148a4ffc17146624&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22background.png%22"></img>

#### Advanced feature
Status bar

Preferences -> Profiles -> Open Profiles -> Edit Profiles -> Session
<img src='https://s3.us-west-2.amazonaws.com/secure.notion-static.com/2adc7cbc-3a86-4e0f-af4d-d02c1160b2f8/bar.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210626%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210626T083315Z&X-Amz-Expires=86400&X-Amz-Signature=9e88a9665664973f9dd83a9f91f407d5443a8c77acbeb7549a8002db15fe43af&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22bar.png%22'></img>


### zsh
Oh My Zsh is an open source, community-driven framework for managing your zsh configuration.
We can install oh my zsh trough ``curl`` or ``wget``.
```bash
# curl
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
# wget
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

I recommend some plugin to improve your develop efficiency.
```bash
# complete
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
# highlight
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# autojump
git clone git://github.com/wting/autojump.git && cd autojump && ./install.py
```
You should config ``plugins`` in ``~/.zshrc`` and run `source ~/.zshrc` to make sure the plugins to take effect.

Theme
```bash
# powerlevel10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
Then, we config ``~/.zshrc``, set ``ZSH_THEME`` to ``powerlevel10k/powerlevel10k`` and source `~/.zshrc`.
### vim

```bash
# ultimate vimrc Awesome version
git clone --depth=1 https://github.com/amix/vimrc.git ~/.vim_runtime
sh ~/.vim_runtime/install_awesome_vimrc.sh

# Vundle is short for Vim bundle and is a Vim plugin manager.
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
vim +PluginInstall +qall

# undo && redo(ctrl+r)
# echo "set undofile" >> ~/.vimrc
# echo "set undodir=~/.vim/undodir" >> ~/.vimrc
mkdir ~/.vim/undodir
```
### tmux

TBD
