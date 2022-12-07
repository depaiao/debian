#
# ~/.bashrc
#

# If not running interactively, don't do anything
[[ $- != *i* ]] && return

### OVERALL CONDITIONALS {{{
		_isxrunning=false
		[[ -n "$DISPLAY" ]] && _isxrunning=true

		_islinux=false
		[[ "$(uname -s)" =~ Linux|GNU|GNU/* ]] && _islinux=true

		_isarch=false
		[[ -f /etc/arch-release ]] && _isarch=true

		_isopensuse=false
		[[ "$(cat /etc/os-release)" =~ openSUSE|opensuse|suse ]] && _isopensuse=true

		_isroot=false
		[[ $UID -eq 0 ]] && _isroot=true

# VARIABLES
		NANO=$(which /usr/bin/nano 2> /dev/null)' -Dlwc'


# PS1 CONFIG {{{
		if $_isxrunning; then
				export TERM='xterm-256color'
#				if $_isroot; then
#						[[ -f /root/.dircolors_256 ]] && eval $(dircolors -b /root/.dircolors_256)
#				else
#						[[ -f $HOME/.dircolors_256 ]] && eval $(dircolors -b $HOME/.dircolors_256)
#		fi
				B='\[\e[1;38;5;33m\]'	#blue
				LB='\[\e[1;38;5;81m\]'	#ligth blue
				GY='\[\e[1;38;5;242m\]'	#gray
				G='\[\e[1;38;5;82m\]'	#green
				P='\[\e[1;38;5;161m\]'	#pink
				PP='\[\e[1;38;5;93m\]'	#purple
				R='\[\e[1;38;5;196m\]'	#red
				Y='\[\e[1;38;5;214m\]'	#yellow
				W='\[\e[0m\]'	      	#white

				get_prompt_symbol() {
				[[ $UID == 0 ]] && echo "#" || echo "\$"
				}
				export PS1="$GY[$Y\u$W@$P\h$GY:$B\W$GY]$W\$(get_prompt_symbol) "
#		else
#		[[ -f $HOME/.dircolors ]] && eval $(dircolors -b $HOME/.dircolors)
fi

# SCRIPTS TO EMBELLISH {{{
		#if $_isroot; then
				#/usr/bin/Nyan.sh
				#/usr/bin/neofetch --cpu_temp C --kernel_shorthand off --shell_path on
				#/usr/bin/pacman_colours.sh
				#/usr/bin/invader.sh
				#/usr/bin/cores.sh
				#/usr/bin/tabela_de_cor.sh
		#else
				#/usr/bin/Nyan.sh
				#/usr/bin/neofetch --cpu_temp C --kernel_shorthand off --shell_path on
				#/usr/bin/pacman_colours
				#/usr/bin/invader.sh
				#/usr/bin/cores.sh
				#/usr/bin/tabela_de_cor.sh
#fi

# }}}
# }}}
# }}}

### BASH OPTIONS {{{
		complete -cf sudo
		shopt -s cdspell                 # Correct cd typos
		shopt -s checkwinsize            # Update windows size on command
		shopt -s histappend              # Append History instead of overwriting file
		shopt -s cmdhist                 # Bash attempts to save all lines of a multiple-line command in the same history entry
		shopt -s extglob                 # Extended pattern
		shopt -s no_empty_cmd_completion # No empty completion

# BASH HISTORY {{{
		export HISTSIZE=10000              # bash history will save N commands
		export HISTFILESIZE=${HISTSIZE}    # bash will remember N commands
		export HISTCONTROL=ignoreboth      # ingore duplicates and spaces
		export HISTIGNORE='&:ls:ll:la:cd:exit:clear:history'
# }}}
# }}}

### EDITOR {{{
#		if which nano &> /dev/null; then
				export EDITOR='$NANO'
				export VISUAL='$EDITOR'
		#elif which vim &>/dev/null; then
		#export EDITOR="vim"
		#else
		#export EDITOR="emacs -nw"
#fi
# }}}

### COLORED MANUAL PAGES {{{
		export PAGER=less
		export LESS_TERMCAP_mb=$'\E[01;31m'         # begin blinking
		export LESS_TERMCAP_md=$'\E[01;38;5;74m'    # begin bold
		export LESS_TERMCAP_me=$'\E[0m'             # end mode
		export LESS_TERMCAP_se=$'\E[0m'             # end standout-mode
		export LESS_TERMCAP_so=$'\E[38;5;246m'      # begin standout-mode - info box
		export LESS_TERMCAP_ue=$'\E[0m'             # end underline
		export LESS_TERMCAP_us=$'\E[04;38;5;146m'   # begin underline
# }}}

### ALIAS {{{
# AUTOCOLOR {{{
		source /$HOME/.dircolors.sh			#https://github.com/trapd00r/LS_COLORS
		alias dir='dir --color=auto'
		alias vdir='vdir --color=auto'
		alias grep='grep --color=auto'
		alias fgrep='fgrep --color=auto'
		alias egrep='egrep --color=auto'

#GRC_ALIASES=true
#[[ -s "/etc/profile.d/grc.sh" ]] && source /etc/profile.d/grc.sh

#		if which grc &> /dev/null; then
#				alias colourify='grc -es --colour=auto'
#				alias blkid='colourify blkid'
#				alias configure='colourify ./configure'
#				alias df='colourify df'
#				alias diff='colourify diff'
#				alias docker='colourify docker'
#				alias docker-machine='colourify docker-machine'
#				alias du='colourify du'
#				alias env='colourify env'
#				alias free='colourify free'
#				alias fdisk='colourify fdisk'
#				alias findmnt='colourify findmnt'
#				alias make='colourify make'
#				alias gcc='colourify gcc'
#				alias g++='colourify g++'
#				alias id='colourify id'
#				alias ip='colourify ip'
#				alias iptables='colourify iptables'
#				alias as='colourify as'
#				alias gas='colourify gas'
#				alias ld='colourify ld'
#				#alias ls='colourify ls'
#				alias lsof='colourify lsof'
#				alias lsblk='colourify lsblk'
#				alias lspci='colourify lspci'
#				alias netstat='colourify netstat'
#				alias ping='colourify ping -c 5'
#				alias traceroute='colourify traceroute'
#				alias traceroute6='colourify traceroute6'
#				alias head='colourify head'
#				alias tail='colourify tail'
#				alias dig='colourify dig'
#				alias mount='colourify mount'
#				alias ps='colourify ps'
#				alias mtr='colourify mtr'
#				alias semanage='colourify semanage'
#				alias getsebool='colourify getsebool'
#				alias ifconfig='colourify ifconfig'
#		fi
# }}}

# LS {{{
		alias ls='ls -hF --color=auto'
		alias lr='ls -R --color=auto'                    # recursive ls
		alias la='ls -ahF --color=auto'
# }}}

# MODIFIED COMMANDS {{{
		alias ..='cd ..'
		alias ...='cd ../..'
		alias ....='cd ../../..'
		alias df='df -h -T'
		alias diff='colordiff'
#		alias du='du -c -h'
		alias du='du -h --max-depth=1 | sort -hr'
		alias free='free -m'			 # show sizes in MB
		alias mkdir='mkdir -p -v'
		alias more='less'
		alias nano='$NANO'
#		alias ping='ping -c 5'
#		if which pycp &> /dev/null; then	# test pycp installed
#				alias mv='pymv -g'
#				alias cp='pycp -g'
#		else
				alias cp='cp -vi'
				alias mv='mv -vi'
#fi
		alias cmatrix='cmatrix -sb'
		alias lsblk='lsblk -o NAME,FSTYPE,SIZE,MOUNTPOINT,LABEL,UUID'
		if $_isroot; then # we're root
				#alias update-grub='grub-mkconfig -o /boot/grub/grub.cfg "$@"'
				alias powersave='cpupower frequency-set -g powersave'
				alias performance='cpupower frequency-set -g performance'
fi
		alias youtube-dl-audio='youtube-dl --extract-audio --audio-format best --audio-quality 0'
		alias dd='dd status=progress'
		alias backup_system='sudo btrfs subvolume snapshot / /.snapshots/$(date +%d%m%Y_%H:%M:%S)'
#		alias backup_system='sudo btrfs subvolume snapshot / /.snapshots/02'
		alias ncdu='ncdu --color dark'


# PRIVILEGED ACCESS {{{
		if ! $_isroot; then # we're not root
				alias sudo='sudo '
				alias scat='sudo cat'
				alias snano='sudo $NANO'
				alias root='sudo su'
				alias reboot='sudo systemctl reboot'
				alias poweroff='sudo systemctl poweroff'
				alias halt='sudo systemctl halt'
				alias suspend='sudo systemctl suspend'
				alias hibernate='sudo systemctl hibernate'
				#alias update-grub='sudo grub-mkconfig -o /boot/grub/grub.cfg "$@"'
				alias powersave='sudo cpupower frequency-set -g powersave'
				alias performance='sudo cpupower frequency-set -g performance'

#alias testing_on='sudo sed -i "/\[.*testing\]/,+1 s/^#*//" /etc/pacman.conf'
#alias testing_off='sudo sed -i "/\[.*testing\]/,+1 s/^/#/" /etc/pacman.conf'

fi
# }}}
# }}}

# PACMAN ALIASES {{{
		if $_isarch; then # we're on Arch
				if ! $_isroot; then # we're not root
						alias pacman='sudo pacman'
		fi
		alias upgrade-aur='yay -Sua --editmenu --upgrademenu --devel --timeupdate' # aur upgrade
fi
# }}}

# ZYPPER ALIASES {{{
		if $_isopensuse; then # we're on openSUSE
				if ! $_isroot; then # we're not root
						alias zypper='sudo zypper -vv'
#				else
#						alias zypper='zypper -vv'
		fi
#		alias clean="zypper packages --unneeded | awk -F'|' 'NR==0 || NR==1 || NR==2 || NR==3 || NR==4 {next} {print $3}' | grep -v Name | sudo xargs zypper remove --clean-deps"
fi
# }}}
# }}}

### FUNCTIONS {{{
# EXTRACT COMPACTE FILES{{{
		extract() {
		if [ -z ${1} ] || [ "$1" = "-h" ] || [ "$1" = "--help" ]; then
				echo "Usage: extract <archive> [directory]"
				echo "Example: extract presentation.zip."
				echo "Valid archive types are:"
				echo "tar.bz2, tar.gz, tar.xz, tar, bz2, gz, tbz2,"
				echo "tbz, tgz, lzo, rar, zip, 7z, xz, txz, lzma and tlz"
		else
				case "$1" in
						*.tar.bz2|*.tbz2|*.tbz)         tar xvjf "$1" ;;
						*.tgz)                          tar zxvf "$1" ;;
						*.tar.gz)                       tar xvzf "$1" ;;
						*.tar.xz)                       tar xvJf "$1" ;;
						*.tar)                          tar xvf "$1" ;;
						*.rar)                          7z x "$1" ;;
						*.zip)                          unzip "$1" ;;
						*.7z)                           7z x "$1" ;;
						*.lzo)                          lzop -d  "$1" ;;
						*.gz)                           gunzip "$1" ;;
						*.bz2)                          bunzip2 "$1" ;;
						*.Z)                            uncompress "$1" ;;
						*.xz|*.txz|*.lzma|*.tlz)        xz -d "$1" ;;
						*) echo "Sorry, '$1' could not be decompressed." ;;
				esac
fi
}
#}}}

# UP {{{
# Goes up many dirs as the number passed as argument, if none goes up by 1 by default
		up() {
		local d=""
		limit=$1
		for ((i=1 ; i <= limit ; i++)); do
		d=$d/..
		done
		d=$(echo $d | sed 's/^\///')
		if [[ -z "$d" ]]; then
				d=..
fi
cd $d
}
#}}}

# FIND A FILE WITH A PATTERN IN NAME {{{
		ff () {
		find . -type f -iname '*'$*'*' -ls ;
}
#}}}

# FIND A FILE WITH PATTERN $1 IN NAME AND EXECUTE $2 ON IT {{{
		fe () {
		find . -type f -iname '*'$1'*' -exec "${2:-file}" {} \;  ;
}
#}}}

## FINDS DIRECTORY SIZES AND LISTS THEM FOR THE CURRENT DIRECTORY {{{
		dirsize () {
		du -shx * .[a-zA-Z0-9_]* 2> /dev/null | egrep '^ *[0-9.]*[MG]' | sort -n > /tmp/list
		egrep '^ *[0-9.]*M' /tmp/list
		egrep '^ *[0-9.]*G' /tmp/list
		rm -rf /tmp/list
}
#}}}

# ENTER AND LIST DIRECTORY{{{
		function cd() { builtin cd -- "$@" && { [ "$PS1" = "" ] || ls; }; }
#}}}

# MIRROR FAST{{{
		mirror-recovery() {
		echo -e "Mirrors will be restored to the most current version in /et/pacman.d/mirrorlisttest"
		if $_isroot; then
				rm -r /etc/pacman.d/mirrorlisttest
				curl -o "https://archlinux.org/mirrorlist/all/" > /etc/pacman.d/mirrorlisttest
fi
}
#}}}
#}}}

### CCACHE {{{ https://wiki.archlinux.org/index.php/Ccache
#		export PATH="/usr/lib/ccache/bin/:$PATH"
#		export PATH="/usr/lib/colorgcc/bin/:$PATH"
#		export CCACHE_PATH="/usr/bin"
#}}}

if which thefuck &> /dev/null; then
	eval "$(thefuck --alias)"
fi











#https://github.com/helmuthdu/dotfiles/blob/master/.bashrc

#setxkbmap -model abnt2 -layout br -variant abnt2 #set keyboard to br-abnt2
#setxkbmap -layout us -variant intl #set beyboard to us-acentos

#powerline see https://wiki.archlinux.org/index.php/Powerline
#powerline-daemon -q
#POWERLINE_BASH_CONTINUATION=1
#POWERLINE_BASH_SELECT=1
#. /usr/share/powerline/bindings/bash/powerline.sh

#/usr/share/clang/bash-autocomplete.sh
PATH=$PATH:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
