---
title: Конфигурация git. Включение подсветки текущей ветки.
author: fatuk
date: 2015-01-12
template: article.jade
tags: git, bash, shell, config
---

Для удобства работы с git включим подсветку текущей ветки. А также добавим стандартные алиасы для git.
<span class="more"></span>

1. Для начала установим git: `sudo apt-get install git`.
2. Добавим стандартные алиасы для команд и данные пользователя:

```bash
#!/bin/bash
git config --global user.name "fatuk" &&
git config --global user.email "fatukk@gmail.com" &&
git config --global color.ui auto &&
git config --global alias.co checkout &&
git config --global alias.ci commit &&
git config --global alias.st status &&
git config --global alias.br branch &&
git config --global alias.hist 'log --pretty=format:"%h %ad | %s%d [%an]" --graph --date=short' &&
git config --global alias.type 'cat-file -t' &&
git config --global alias.dump 'cat-file -p'

```
Теперь настроим bash, чтобы он нам показывал текущую ветку:
* Создадим в домашнем каталоге файл `.bash-git`

```bash
function parse_git_branch {
	git branch --no-color 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}

function proml {
	local        BLUE="\[\033[0;34m\]"
	local         RED="\[\033[0;31m\]"
	local      YELLOW="\[\033[0;33m\]"
	local   LIGHT_RED="\[\033[1;31m\]"
	local       GREEN="\[\033[0;32m\]"
	local LIGHT_GREEN="\[\033[1;32m\]"
	local  LIGHT_GRAY="\[\033[0;37m\]"
	case $TERM in
		xterm*)
		TITLEBAR='\[\033]0;\u@\h:\w\007\]'
		;;
		*)
		TITLEBAR=""
		;;
	esac

PS1="$PS1$YELLOW\$(parse_git_branch)$LIGHT_GRAY"
PS2='> '
PS4='+ '
}

proml
```
* Откроем файл `~/.bashrc` и добавим в конец этого файла строку: `source ${HOME}/.bash-git`
* Перезапускаем shell и вуаля, теперь мы видим название текущей ветки.

### Полезные ссылки:
* [set-git-config](https://gist.github.com/f6f82f95746b67209e16.git)
* [.bashrc](https://gist.github.com/9585750.git)
