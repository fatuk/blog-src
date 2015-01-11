---
title: Как сгенерировать SSH ключ для Github.
author: fatuk
date: 2015-01-12
template: article.jade
tags: git, github, ssh-key
---

Для того чтобы каждый раз не логиниться, при отправке изменений на удаленный сервер, нам понадобится SSH ключ.
<span class="more"></span>

* `ssh-keygen -t rsa -C "your_email@example.com"`
* Enter
* Enter
* Enter

Готово. В домашнем каталоге в папке `.ssh` находятся сгенерированные файлы ключей: `id_rsa` и `id_rsa.pub`.
Нам нужен второй файл. Открываем его в редакторе, копируем его содержимое.

Заходим на страницу настрое Github [https://github.com/settings/ssh](https://github.com/settings/ssh). Нажимаем **Add SSH key**, указываем любое название ключа, в поле ниже вставляем содержимого нашего публичного ключа. Теперь можно использовать SSH (`git@github.com:fatuk/fatuk.github.com.git`).

[Источник](https://help.github.com/articles/generating-ssh-keys/)
