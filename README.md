# My Git Config

## Normal Settings
```INI
[commit]
	gpgsign = true
[core]
	editor = code

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

	# Checkout
	co = checkout
	cob = checkout -b
	
	# Fetch, push, pull and remote
	p = push
	fp = fetch -p
	rao = remote add origin
	pushit = push -u origin --all
	
	# Commit
	c = commit -m
	m = commit --amend -m
	ca = commit -a --verbose
	ac = !git add . && git commit -m
	
	# Branch
	ba = branch -a
	bd = branch -d
	bD = branch -D
	
	#diff
	d = diff
	ds = diff --stat
	dc = diff --cached

	# Feature improving aliases
	a = add
	ap = add -p
	st = status -sb
	
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
