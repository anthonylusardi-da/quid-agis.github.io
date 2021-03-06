---
layout: default
title: The Blog of Quid Agis / Configs
---
### Configurations page

Current ~/.bash_aliases [Download](/assets/docs/bash_aliases.txt)

```
## SYSTEM commands

alias ..='cd ..'
alias ad='sudo apt install --dry-run'
alias ag='sudo apt upgrade'
alias agd='sudo apt upgrade --dry-run'
alias ai='sudo apt install'
alias ar='sudo apt autoremove'
alias at='sudo apt dist-upgrade'
alias au='sudo apt update'
alias bi='cd /home/quid/.bin && clear && pwd && ls -al'
alias cdl='cd /home/quid/Linux_OS_Dev && clear && pwd && ls'
alias cds='cd /home/quid/Storage/ && clear && pwd && ls'
alias cl='clear'
alias cw='cd ~/Downloads && clear && ls'
alias dis='/bin/bash /home/quid/.bin/daml_info_svc.sh'
alias dl='dpkg --list | grep'
alias dli='dpkg --list | grep ii | grep lib | less'
alias hc='history -c && clear'
alias hh='history | less'
alias hx='history -c && clear && exit'
alias lg='ls -al | grep '
alias lh='ls -hl'
alias ll='ls -al'
alias llh='ls -hl | less'
alias lll='ls -al | less'
alias mk='/usr/bin/mkdir -p'
alias na='nano ~/.bash_aliases'
alias nb='nano ~/.bashrc'
alias nd='nano ~/.bin/daml_info_svc.sh'
alias ni='nano ~/.irssi/config'
alias np='nano ~/.profile'
alias nv='nano ~/.vimrc'
alias nvb='cp -v ~/.vimrc ~/.vimrc.backup'
alias nvv='cp -v ~/.vimrc.backup ~/.vimrc'
alias nvvm='cp -v ~/.vimrc ~/.vimrc.master'
alias nvnew='cp -v ~/.vimrc.new ~/.vimrc'
alias pba='cd ~/Projects/bash && clear && pwd && ls'
alias pda='cd ~/Projects/daml && clear && pwd && ls'
alias pwh='python3 -m http.server 8000 --directory ~/'
alias pws='python3 -m http.server 8000 --directory ~/Documents/'
alias pww='python3 -m http.server 8000'
alias py='/usr/bin/python3'
alias py3='/usr/bin/python3'
alias sb='source ~/.bashrc'
alias sp='source ~/.bash_profile'
alias sd='sudo shutdown -h now'
alias sr='sudo shutdown -r now'
alias tm='tmux new -s Comms'
alias top='/usr/bin/htop'
alias xt='/usr/bin/xterm'
alias xx='/usr/bin/xsel -bc'
alias ya='/usr/bin/youtube-dl --abort-on-error '

## PROJECT commands

alias pd='cd /home/quid/Projects/daml/ && clear && pwd && ls'
alias pj='cd ~/Projects && clear && ls'

## MOUNT commands

alias m1='sudo mount -l --types=ext4 /dev/sdb1 /home/quid/Linux_OS_Dev/'
alias um1='sudo umount /dev/sdb1'
alias cm1='mount | grep sdb'
alias m2='sudo mount -l --types=ext4 /dev/sdc1 /home/quid/Storage/'
alias um2='sudo umount /dev/sdc1'
alias cm2='mount | grep sdc'

## NETWORK commands

UNDEVBOX [192.168.1.150]
alias p50='ping undevbox'
alias s50='ssh -p 7913 quid@undevbox'

DPILEDGER [192.168.1.160]
alias p60='ping dpiledger'
alias s60='ssh -p 7913 dietpi@dpiledger'

DPINODE01 [192.168.1.165]
alias p65='ping dpinode01'
alias s65='ssh -p 7913 dietpi@dpinode01'

ROUTER [192.168.1.254]
alias pmm='ping router'

## QUIDAGIS

alias qab='cp -rv ~/Git/quid-agis.github.io/ ~/Git/backup_quidagis/'
alias qad='rm -rf ~/Git/backup_quidagis/quid-agis.github.io/'
alias qas='bundle exec jekyll serve --livereload'
alias qau='bundle update'
alias qaw='cd ~/Git/quid-agis.github.io && clear && pwd && ls -al'

## MISC

# cat /etc/X11/default-display-manager
# echo $XDG_CURRENT_DESKTOP
# Turn X on ... systemctl set-default graphical.target
# Turn X off ... systemctl set-default multi-user.target
# gst-launch-1.0 playbin uri=file:/home/quid/Downloads/Market-in-a-Box_webinar_IEU.mp4
```
Current ~/.bashrc [Download](/assets/docs/bashrc.txt)
```
# ~/.bashrc: executed by bash(1) for non-login shells.
# see /usr/share/doc/bash/examples/startup-files (in the package bash-doc)
# for examples

# If not running interactively, don't do anything
case $- in
    *i*) ;;
      *) return;;
esac

# don't put duplicate lines or lines starting with space in the history.
# See bash(1) for more options
HISTCONTROL=ignoreboth

# append to the history file, don't overwrite it
shopt -s histappend

# for setting history length see HISTSIZE and HISTFILESIZE in bash(1)
HISTSIZE=1000
HISTFILESIZE=2000

# check the window size after each command and, if necessary,
# update the values of LINES and COLUMNS.
shopt -s checkwinsize

# If set, the pattern "**" used in a pathname expansion context will
# match all files and zero or more directories and subdirectories.
#shopt -s globstar

# make less more friendly for non-text input files, see lesspipe(1)
[ -x /usr/bin/lesspipe ] && eval "$(SHELL=/bin/sh lesspipe)"

# set variable identifying the chroot you work in (used in the prompt below)
if [ -z "${debian_chroot:-}" ] && [ -r /etc/debian_chroot ]; then
    debian_chroot=$(cat /etc/debian_chroot)
fi

# set a fancy prompt (non-color, unless we know we "want" color)
case "$TERM" in
    xterm-color|*-256color) color_prompt=yes;;
esac

# uncomment for a colored prompt, if the terminal has the capability; turned
# off by default to not distract the user: the focus in a terminal window
# should be on the output of commands, not on the prompt
#force_color_prompt=yes

if [ -n "$force_color_prompt" ]; then
    if [ -x /usr/bin/tput ] && tput setaf 1 >&/dev/null; then
	# We have color support; assume it's compliant with Ecma-48
	# (ISO/IEC-6429). (Lack of such support is extremely rare, and such
	# a case would tend to support setf rather than setaf.)
	color_prompt=yes
    else
	color_prompt=
    fi
fi

if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u \[\033[01;34m\]\w\[\033[00m\] \$ '
#    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\] \[\033[01;34m\]\w\[\033[00m\] \$ '
#    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u \h \[\033[01;34m\]\w\[\033[00m\] \$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
fi
unset color_prompt force_color_prompt

# If this is an xterm set the title to user@host:dir
case "$TERM" in
xterm*|rxvt*)
    PS1="\[\e]0;${debian_chroot:+($debian_chroot)}\u@\h: \w\a\]$PS1"
    ;;
*)
    ;;
esac

# enable color support of ls and also add handy aliases
if [ -x /usr/bin/dircolors ]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
    alias ls='ls --color=auto'
    alias dir='dir --color=auto'
    alias vdir='vdir --color=auto'

    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi

# colored GCC warnings and errors
#export GCC_COLORS='error=01;31:warning=01;35:note=01;36:caret=01;32:locus=01:quote=01'

# some more ls aliases
# alias ll='ls -alF'
# alias la='ls -A'
# alias l='ls -CF'

# Add an "alert" alias for long running commands.  Use like so:
#   sleep 10; alert
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'

# Alias definitions.
if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi

# Completion
if ! shopt -oq posix; then
  if [ -f /usr/share/bash-completion/bash_completion ]; then
    . /usr/share/bash-completion/bash_completion
  elif [ -f /etc/bash_completion ]; then
    . /etc/bash_completion
  fi
fi

# $user settings
export GEM_HOME="$HOME/gems"
export JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64
[ -f "/home/quid/.ghcup/env" ] && source "/home/quid/.ghcup/env" # ghcup-env
[ -f "~/.fzf.bash" ] && source "~/.fzf.bash"

#Extra $user paths

export PATH="$HOME/.bin:$PATH"
export PATH="$HOME/.daml/bin:$PATH"
export PATH="$HOME/.local/bin:$PATH"
export PATH="$HOME/.yarn/bin:$HOME/.config/yarn/global/node_modules/.bin:$PATH"
export PATH="$HOME/bin:$PATH"
export PATH="$HOME/gems/bin:$PATH"
export PAGER="most"

# EOF
```
