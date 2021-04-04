---
layout: default
title: The Blog of Quid Agis / Configs
---
## Configurations page

Current ~/.bash_aliases

#### SYSTEM commands
```
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
```

#### PROJECT commands
```
alias pd='cd /home/quid/Projects/daml/ && clear && pwd && ls'
alias pj='cd ~/Projects && clear && ls'
```

#### MOUNT commands
```
alias m1='sudo mount -l --types=ext4 /dev/sdb1 /home/quid/Linux_OS_Dev/'
alias um1='sudo umount /dev/sdb1'
alias cm1='mount | grep sdb'
alias m2='sudo mount -l --types=ext4 /dev/sdc1 /home/quid/Storage/'
alias um2='sudo umount /dev/sdc1'
alias cm2='mount | grep sdc'
```

#### NETWORK commands
```
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
```

#### QUIDAGIS
```
alias qab='cp -rv ~/Git/quid-agis.github.io/ ~/Git/backup_quidagis/'
alias qad='rm -rf ~/Git/backup_quidagis/quid-agis.github.io/'
alias qas='bundle exec jekyll serve --livereload'
alias qau='bundle update'
alias qaw='cd ~/Git/quid-agis.github.io && clear && pwd && ls -al'
```

#### MISC
```
# cat /etc/X11/default-display-manager
# echo $XDG_CURRENT_DESKTOP
# Turn X on ... systemctl set-default graphical.target
# Turn X off ... systemctl set-default multi-user.target
# gst-launch-1.0 playbin uri=file:/home/quid/Downloads/Market-in-a-Box_webinar_IEU.mp4
```
