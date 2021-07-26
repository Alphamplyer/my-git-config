# My Git Config

## Normal Settings
```INI
[commit]
	gpgsign = true
[core]
	# uncomment for Linux
	editor = code

	# uncomment for Windows
	# editor = \"C:\\Users\\Alphamplyer\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe\" --wait

	# set autocrlf option to :
	#   -  'input' if you are on a Linux distribution
	#   -  'true' if you are on Windows and work also with Linux projects
        #   -  'false' if you are on Windows and work only with Windows projects  
	autocrlf = input
[color]
	branch = auto
	diff = auto
	interactive = auto
	status = auto
	grep = auto
[credential]
	helper = store --file ~/.my-credentials
```

## Alias
```INI
[alias]
	# one-line log
	l = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short

	# Git to Github
	g2gh = !git branch -M main && git remote add origin

	# Checkout
	co = checkout
	cob = checkout -b
	
	# Fetch, push, pull and remote
	rao = remote add origin
	fp = fetch -p
	p = push
	pushit = push -u origin --all
	
	# Commit
	ac = !git add . && git commit -m
	c = commit -m
    	ca = commit -a --verbose
    	m = commit --amend -m
	
	# Branch
	ba = branch -a
	bd = branch -d
	bD = branch -D
	dc = diff --cached
	
	#diff
	d = diff
	ds = diff --stat
	dc = diff --cached

	# Feature improving aliases
	st = status -sb
	a = add
	ap = add -p
	
	# list aliases
	la = "!git config -l | grep alias | cut -c 7-"
	
	# list branches sorted by last modified
	b = "!git for-each-ref --sort='-authordate' --format='%(authordate)%09%(objectname:short)%09%(refname)' refs/heads | sed -e 's-refs/heads/--'"

	# Complex aliases
	plog = log --graph --pretty='format:%C(red)%d%C(reset) %C(yellow)%h%C(reset) %ar %C(green)%aN%C(reset) %s'
	tlog = log --stat --since='1 Day Ago' --graph --pretty=oneline --abbrev-commit --date=relative
	lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
	rank = shortlog -sn --no-merges
	bdm = "!git branch --merged | grep -v '*' | xargs -n 1 git branch -d"
```
