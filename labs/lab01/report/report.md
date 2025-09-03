---
## Front matter
title: "Отчёт по лабораторной работе №1"
subtitle: "Работа с виртуальной машиной"
author: "Александр Андриевский"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---
# Цели и задачи работы

# Цель лабораторной работы
Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.



# Ход выполнения

 


## Создание виртуальной машины

![Создание виртуальной машины 1](images/img.png)

## Создание пользователя в VirtualBox

![Создание пользователя в VirtualBox](images/img_1.png)

## Завершение установки и настройка имени хоста

![Завершение установки и имя хоста](images/img_2.png)

## Добавление общей папки

![Добавление общей папки](images/img_3.png)

## Установка гостевых дополнений

![Установка гостевых дополнений](images/img_4.png)


## Проверка наличия общей папки в /media

![Появление общей папки /media/sf_wor](images/img_5.png)

# Выводы по проделанной работе

## Вывод

Мы приобрели практические навыки работы с созданием виртуальной машиной

# Выводы по проделанной работе

## Вывод

Мы приобрели практические навыки работы с созданием виртуальной машиной