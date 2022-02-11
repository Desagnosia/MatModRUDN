---
# Front matter
title: "Отчёт по лабораторной работе 1"
subtitle: "Математическое моделирование"
author: "Юхнин Илья Андреевич"

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
### Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---
# Цель работы

Научиться работе с Git и языком разметки Markdown

# Задание

Создание отчёта по предыдущей лабораторной работе Git в формате Markdown

# Теоретическое введение

Git — это система контроля версий, которая позволяет отслеживать и фиксировать изменения в коде: вы можете восстановить код в случае сбоя или откатить до более ранних версий. С Git работают через командную строку или инструменты вроде GitHub. Команды Git принимают вид git <команда> <аргументы>, где аргументом может быть путь к файлу. В команды также включаются опции, которые обозначаются как --<опция>.

Markdown — это синтаксис (или набор правил), который форматирует текст на веб-страницах. Markdown упрощает форматирование текста для веб-страниц, поскольку теги проще, чем HTML, и они автоматически преобразуются в HTML. Это означает, что вам не нужно знать HTML, чтобы написать что-то для веб-страницы, потому что Markdown переводит ваши теги в HTML для вас. Он охватывает не все возможные теги HTML, а наиболее распространенные параметры форматирования.

# Выполнение лабораторной работы

1.1 Подготовка работы с git(рис. 1.1)

![1.1](img/1.1.PNG)

1.2 Создание проекта и добавление его в репозиторий(рис. 1.2)

![1.2](img/1.2.PNG)

1.3 Внесение изменений и проверка состояния рабочего каталога(рис. 1.3)

![1.3](img/1.3.PNG)

1.4 Индексация изменений и работа с историей и тегами(рис. 1.4.1-3 - 1.4.5-7)

![1.4.1-3](img/1.4.1-3.PNG)

![1.4.4](img/1.4.4.PNG)

![1.4.5-7](img/1.4.5-7.PNG)

1.5 Отмена локальных изменений (до индексации) (рис. 1.5)

![1.5](img/1.5.PNG)

1.6 Отмена проиндексированных изменений (перед коммитом)(рис. 1.6)

![1.6](img/1.6.PNG)

1.7 Отмена коммитов(рис. 1.7)

![1.7](img/1.7.PNG)

1.8 Удаление коммиттов из ветки(рис. 1.8.2-3 - 1.8.5)

![1.8.2-3](img/1.8.2-3.PNG)

![1.8.4](img/1.8.4.PNG)

![1.8.5](img/1.8.5.PNG)

1.9 Удаление тега oops (рис. 1.9)

![1.9](img/1.9.PNG)

1.10 Внесение изменений в коммиты(рис. 1.10)

![1.10](img/1.10.PNG)

1.11 Перемещение файлов(рис. 1.11)

![1.11](img/1.11.PNG)

1.12 Второй способ перемещения файлов(рис. 1.12)

![1.12](img/1.12.PNG)

1.13 Подробнее о структуре(добавление index.html)(рис. 1.13)

![1.13](img/1.13.PNG)

1.14 Каталог .git(рис. 1.14)

![1.14](img/1.14.PNG)

1.15 Работа непосредственно с объектами git(рис. 1.15а - 1.15b)

![1.15a](img/1.15a.PNG)

![1.15b](img/1.15b.PNG)

1.16 Создание ветки(рис. 1.16)

![1.16](img/1.16.PNG)

1.17 Навигация по веткам(рис. 1.17)

![1.17](img/1.17.PNG)

1.18 Изменения в ветке master(рис. 1.18)

![1.18](img/1.18.PNG)

1.19 Создание коммит изменений README.md в ветку master(рис. 1.19)

![1.19](img/1.19.PNG)

1.20 Слияние веток(рис. 1.20)

![1.20](img/1.20.PNG)

1.21 Создание конфликта(рис. 1.21)

![1.21](img/1.21.PNG)

1.22 Разрешение конфликтов(рис. 1.22)

![1.22](img/1.22.PNG)

1.23 Сброс ветки style(рис. 1.23)

![1.23](img/1.23.PNG)

1.24 Сброс ветки master(рис. 1.24)

![1.24](img/1.24.PNG)

1.25 Перебазирование(рис. 1.25)

![1.25](img/1.25.PNG)

1.26 Слияние в ветку master(рис. 1.26)

![1.26](img/1.26.PNG)

1.27 Клонирование репозиториев(рис. 1.27)

![1.27](img/1.27.PNG)

1.28 Просмотр клонированного репозитория(рис. 1.28)

![1.28](img/1.28.PNG)

1.29 Origin(рис. 1.29)

![1.29](img/1.29.PNG)

1.30 Удаленные ветки(рис. 1.30)

![1.30](img/1.30.PNG)

1.31 Изменение оригинального репозитория(рис. 1.31)

![1.31](img/1.31.PNG)

1.32 Слияние извлеченных изменений(рис. 1.32)

![1.32](img/1.32.PNG)

1.33 Добавление ветки наблюдения(рис. 1.33)

![1.33](img/1.33.PNG)

1.34-1.35 Создание чистого репозитория(рис. 1.35)

![1.35](img/1.35.PNG)

1.36 Добавление удаленного репозитория(рис. 1.36)

![1.36](img/1.36.PNG)

1.37 Отправка изменений(рис. 1.37)

![1.37](img/1.37.PNG)

1.38 Извлечение общих изменений(рис. 1.38)

![1.38](img/1.38.PNG)


# Выводы

В результате проделанной лабораторной работы, познакомился с работой распределённой системы управления версиям Git, а также с языком разметки Markdown