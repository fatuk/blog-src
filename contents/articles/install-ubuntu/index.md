---
title: Как установить Ubuntu
author: fatuk
date: 2015-01-06
template: article.jade
tags: ubuntu, howto
---

![Ubuntu logo](ubuntu-logo.svg)

Пошаговая инструкция по установке Ubuntu 12.04 - 14.10
<span class="more"></span>

## Предисловие

Если планируется использовать Windows как вторую систему, то она должна быть предустановлена. В противном случае Windows не позволит загрузить [GRUB](http://help.ubuntu.ru/wiki/grub) и не будет выбора системы при загрузке.

## Скачать Ubuntu
Выбрать и скачать подходящий [образ Ubuntu](http://www.ubuntu.com/download/desktop). Образ записать на диск или [создать](http://help.ubuntu.ru/wiki/unetbootin) загрузочную флешку.

## Разметка диска
Диск размечается следующим образом:

| Mount | Формат     | Размер | Примечание                                       |
| -     | -          | -      | -                                                |
| root  | ext4       | 50 GB  | -                                                |
| swap  | linux-swap | 8 GB   | равен оперативной памяти, нужен для режима "сна" |
| home  | ext4       | 30 GB  | все остальное не менее 30 GB                     |

Для разметки можно воспользоваться программой [GParted](https://ru.wikipedia.org/wiki/GParted), которая доступна при загрузке с Ubuntu LiveCD.