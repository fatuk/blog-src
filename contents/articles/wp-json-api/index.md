---
title: API сервер на WordPress
author: fatuk
date: 2015-03-22
template: article.jade
tags: wordpress, plugin, api
---

![wordpress](wp-logo.png)

Недавно понадобилось получать данные о записях в WordPress в виде JSON. Выбор пал на [JSON API](https://wordpress.org/plugins/json-api/). Он позволяет получать любые данные о записях, страницах, кастомных полях, а также фильтровать их по категориям, слагам и т.д. Под катом идут частные случаи использования данного плагина.
<span class="more"></span>

| Пример                                                                            | Описание                                      |
| :-------------------                                                              | :------                                       |
| `?json=get_posts&category_name=cats&custom_fields=my-custom-field&meta_value=red` | Посты по категории и значению кастомного поля |
| `?json=get_posts`                                                                 | Все посты                                     |
| `?json=get_tag_posts&tag_slug=banana`                                             | Посты по тегу                                 |
| `?json=get_recent_posts`                                                          | Недавние посты                                |
| `?json=get_post&post_id=47`                                                       | Пост по id                                    |
| `http://www.example.org/api/get_post/?post_id=47`                                 | Пример user-friendly ссылки                   |
| `http://www.example.org/api/get_tag_posts/?tag_slug=banana`                       | Пример user-friendly ссылки                   |



Полная [документация](https://wordpress.org/plugins/json-api/other_notes/) по плагину.
