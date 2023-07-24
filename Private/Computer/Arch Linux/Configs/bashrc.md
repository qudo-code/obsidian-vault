```
#
# ~/.bashrc
#

# If not running interactively, don't do anything
[[ $- != *i* ]] && return

alias erc="vim ~/.bashrc"
alias src="source ~/.bashrc"
alias cp="cat $1 | xclip -selection clipboard && echo \"Copied {$1}\""
alias ls='ls --color=auto'
alias grep='grep --color=auto'
alias sound="alsamixer"
alias obsidian="obsidian & disown"

PS1='[\u@\h \W]\$ '

export PATH="/bin/obsidian:$PATH"
```