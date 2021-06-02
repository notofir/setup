# setup
## Mac
```bash
curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh
xcode-select --install

# oh-my-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" "" --unattended
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
brew tap homebrew/cask-fonts
brew install --cask font-hack-nerd-font

# oh-my-tmux
brew install tmux
git clone https://github.com/gpakosz/.tmux.git
ln -s -f .tmux/.tmux.conf
cp .tmux/.tmux.conf.local .

brew install --cask {visual-studio-code thunderbird google-chrome firefox}
brew install {clang-format docker kubectl minikube buildifier go fish reattach-to-user-namespace}

# vim
## vimrc
git clone --depth=1 https://github.com/amix/vimrc.git ~/.vim_runtime
sh ~/.vim_runtime/install_awesome_vimrc.sh
## Plugins
git clone https://github.com/fatih/vim-go.git .vim_runtime/my_plugins/vim-go
git clone https://github.com/bazelbuild/vim-bazel.git .vim_runtime/my_plugins/vim-bazel
git clone https://github.com/google/vim-maktaba.git .vim_runtime/my_plugins/vim-maktaba
git clone https://github.com/skanehira/docker.vim.git .vim_runtime/my_plugins/docker.vim
python3 ~/.vim_runtime/update_plugins.py
```

Changes to ~/.tmux.conf.local:
```
# Set to true:
tmux_conf_copy_to_os_clipboard=true

# Uncomment
set -g status-keys vi
set -g mode-keys vi
```
