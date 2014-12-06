---
title: Page Speed. Проверка оптимизации сайта.
author: fatuk
date: 2014-12-06
template: article.jade
tags: node.js, page speed, оптимизация
---

Попалась на глаза *cli* для сервиса Google [Page Speed](https://developers.google.com/speed/pagespeed/). Он показывает на сколько ваш сайт оптимизирован. Автор -- [Эдди Османи](https://github.com/addyosmani).

<span class="more"></span>

Установим пакет для node.js:

```shell
sudo npm i -g psi
```

Теперь достаточно написать в консоли:

```shell
psi site-for-testing.com
```

После чего в консоли появится оценка сайта с точки зрения оптимизации. Также будет расписан каждый пункт.

```shell
psi github.com

----------------------------------------------------------------

URL:       https://github.com/
Score:     82
Strategy:  desktop

Number Resources                                 | 22
Number Hosts                                     | 5
Total Request                                    | 3.38 kB
Number Static Resources                          | 16
Html Response                                    | 18.18 kB
Css Response                                     | 427.35 kB
Image Response                                   | 889.49 kB
Javascript Response                              | 632.95 kB
Other Response                                   | 76 B
Number Js Resources                              | 4
Number Css Resources                             | 2
                                                 |
Avoid Landing Page Redirects                     | 0
Enable Gzip Compression                          | 0
Leverage Browser Caching                         | 0.5
Main Resource Server Response Time               | 0
Minify Css                                       | 0
Minify HTML                                      | 0
Minify Java Script                               | 0.12
Minimize Render Blocking Resources               | 12
Optimize Images                                  | 6.81
Prioritize Visible Content                       | 0

----------------------------------------------------------------
```

Также есть различные параметры, например проверка под мобильные устройства:

```shell
psi github.com --strategy mobile
```

---

### Полезные ссылки:

* Кто не любит консоль -- можно установить [расширение](https://developers.google.com/speed/pagespeed/insights_extensions) для Хрома
* Про пункты результатов проверки почитать можно [тут](https://developers.google.com/speed/docs/insights/rules)