# Enable Powerlevel10k instant prompt. Should stay close to the top of ~/.zshrc.
# Initialization code that may require console input (password prompts, [y/n]
# confirmations, etc.) must go above this block; everything else may go below.
if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi

# If you come from bash you might have to change your $PATH.
# export PATH=$HOME/bin:/usr/local/bin:$PATH

# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
# ZSH_THEME="steeef" # robbyrussell lambda wedisagree steeef

CASE_SENSITIVE="false"
HYPHEN_INSENSITIVE="true"

zstyle ':omz:update' mode reminder  # just remind me to update when it's time
zstyle ':omz:update' frequency 13

ENABLE_CORRECTION="true"

DISABLE_UNTRACKED_FILES_DIRTY="true"

HIST_STAMPS="dd.mm.yyyy"

plugins=(git asdf)
plugins=(git)

# oh-my-zsh
export ZSH="$HOME/.oh-my-zsh"
source $ZSH/oh-my-zsh.sh

# asdf
source $HOME/.asdf/asdf.sh

# zsh-syntax-highlighting
source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh

# Powerlevel10k
source /usr/local/share/powerlevel10k/powerlevel10k.zsh-theme

# To customize prompt, run `p10k configure` or edit ~/.p10k.zsh.
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh

# User configuration

# Aliases

# Show running processes sorted by memory consumption
alias psmem="ps -axo %mem,pid,comm | sort -nr | head -n 20"

# Functions

#  Kill a process on given port. Uses `kill -9`, which may cause errors
killport() { lsof -t -i :$1 | xargs kill -9 }

# Scripts
export PATH="$PATH:~/bin$"

# Software development configurations

# asdf
export PATH="$PATH:${ASDF_DATA_DIR:-$HOME/.asdf}/shims"
# export PATH="${ASDF_DATA_DIR:-$HOME/.asdf}/shims:$PATH"

# Java
export PATH="$PATH:/usr/bin/java"
export JAVA_HOME=$(/usr/libexec/java_home)

# Flutter
export PATH="$PATH:`pwd`/.development/flutter/bin"

# Ruby
export RUBY_CONFIGURE_OPTS="--with-zlib-dir=$(brew --prefix zlib) --with-openssl-dir=$(brew --prefix openssl) --with-readline-dir=$(brew --prefix readline) --with-libyaml-dir=$(brew --prefix libyaml)"
export RUBY_CFLAGS="-Wno-error=implicit-function-declaration"

alias ruby="$(asdf which ruby)"
alias rails="$(which rails)"

alias ls="eza --color=always --long --icons=always --no-user"
alias cd="z"

eval "$(zoxide init zsh)"

# Game-Porting Toolkit
wine-gptk(){ WINEESYNC=1 WINEPREFIX=~/my-game-prefix $(brew --prefix game-porting-toolkit)/bin/wine64 "$@"; }

# Kubernetes
# source <(kubectl zsh)
