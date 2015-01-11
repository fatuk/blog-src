---
title: Ubuntu. Установка/удаление Apache2 + php5 + MySQL
author: fatuk
date: 2015-01-11
template: article.jade
tags: ubuntu, apache, php, установка, LAMP
---

Оставлю здесь, чтобы не забыть...
<span class="more"></span>

## Установка Apache
* Обновим информацию о пакетах: `sudo apt-get update`
* Обновим систему: `sudo apt-get upgrade`
* Установим apache: `sudo apt-get install apache2`
* Запустим апач: `sudo service apache2 start`

## Работа с Apache
| значение   | команда                        |
| -          | -                              |
| запуск     | `sudo service apache2 start`   |
| остановка  | `sudo service apache2 stop`    |
| перезапуск | `sudo service apache2 restart` |

## Установим PHP:
* `sudo apt-get install php5 libapache2-mod-php5`

## Установим MySQL:
* `sudo apt-get install mysql-server`
* Замена пароля к серверу БД:
	* `sudo mysqladmin -u root password новый_пароль`

## Удаление

### Удаляем пакеты в обратном порядке:
* `sudo apt-get purge php5-mysql`
* `sudo apt-get purge php5`
* `sudo apt-get purge mysql-server`
* `sudo apt-get purge apache2`

### Удаляем зависимости:
* `sudo apt-get purge apache2.2-common`
* `sudo apt-get purge apache2-mpm-prefork`
* `sudo apt-get purge libapache2-mod-php5`

### Удаляем зависимости:
* `/etc/apache2/`
* `/etc/php5/apache2/`



## Источник

[http://start.besthost.by/post/86](http://start.besthost.by/post/86)
