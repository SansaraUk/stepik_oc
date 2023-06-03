---
## Front matter
title: "Stepik: введение в Linux"
subtitle: "Прохождение курса"
author: "Уханаева Сансара Зоригтуевна"

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

# Элементы отчета


## Цели и задачи

Приобрести простейшие навыки разработки, анализа, тестирования и отладки приложений в ОС типа UNIX/Linux на примере создания на языке программирования с помощью курса на stepik. 


## Содержание 

I.

-Что такое виртуальная машина?
- Специальная программа для запуска одной ОС на другой ОС
!(image/1.png)

-Смогли ли вы запустить на своем компьютере Linux?
-Да
!(image/2.png)

-Какое расширение имеют установочные пакеты в Linux (Ubuntu)?
-deb
!(image/3.png)

-Запустите, откройте Help → About (или Shift+F1) и напишите ниже первую фамилию (без имени!) из вкладки Authors. Обратите внимание, что в англоязычных текстах обычно имя стоит на первом месте (first name), а фамилия на втором (last name).
-Denis-Courmont
!(image/4.png)

-Выберите все синонимы для “командной строки”.
-Консоль, Терминал
!(image/5.png)

-Какая команда напечатает в какой директории мы сейчас находимся?
-Только pwd
!(image/6.png)

-Укажите, какие из следующих команд полностью эквивалентны команде ls -A --human-readable -l /some/directory
-ls --almost-all --human-readable -l /some/directory

ls --human-readable -A  -l /some/directory

ls -Ahl /some/directory

ls -lAh /some/directory

ls -h -A -l /some/directory

!(image/7.png)

-Предположим, что вы находитесь в директории /home/bi/Documents, причем /home/bi — ваша домашняя директория. Какая(ие) команда выведет содержимое /home/bi/Downloads, при этом не показывая содержимое других директорий?
-ls ./../Downloads
!(image/8.png)

-Какая команда используется для удаления директорий?
-rm -r
!(image/9.png)

-Что произойдет, если ввести в терминал команду firefox (для запуска одноименного браузера), а затем ввести туда же команду exit?
-Никто не закроется, потому что при включенном firefox терминал нре будет выполнять любые команды
!(image/10.png)

-Чему эквивалентен запуск программы с &?
-Запуск, Ctrl+Z, bg
!(image/11.png)

-Куда по умолчанию выводится поток ошибок из программы, запущенной в терминале?
-На экран
!(image/12.png)

-Какие (какая) из команд создадут файл file.txt и запишут в него поток ошибок программы program? Считайте, что в момент запуска программы файл file.txt не существует.
-program 2>> file.txt; program 2> file.txt
!(image/13.png)

-Куда деваются сообщения об ошибках (т.е. вывод в stderr) от тех программ, которые объединены в конвейер (pipe)?
-Выводятся на экран
!(image/14.png)

-В каком файле на диске окажется картинка, если для её скачивания были выполнены следующие команды?
cd /home/alex/
wget -P /home/alex/Pictures -O 1.jpg http://example.com/example.jpg
-/home/alex/1.jpg
!(image/14.png)

-Какую опцию нужно указать команде wget, чтобы она не выводила никаких сообщений на экран (Resolving.., Connecting to.. и т.д.)?
--q или --quiet
!(image/15.png)

-Пусть на некоторой web-странице есть ссылки на картинки в форматах png и jpg, а также ссылки на другие страницы сайта (обычные html файлы). Какие файлы будут скачаны на компьютер, если запустить wget -r -l 1 -A jpg и передать в качестве аргумента ссылку на эту web-страницу? Выберите наиболее полный ответ!
-Будут скачаны jpg и html файлы, но все html будут удалены
!(image/16.png)


-Чем отличаются архиваторы gzip и zip?
-gzip удаляет архив после его распаковки
!(image/17.png)


-Какие из перечисленных программ-архиваторов могут создать архив из директории с файлами?
-zip, tar
!(image/18.png)


-Какой набор опций нужно указать программе tar, чтобы запаковать файлы в my_archive.tar.bz2?
--cjf
!(image/19.png)


-Какая маска команды find НЕ найдет файл Alexey.jpeg?
-alexey.*; *.jpg; *.?
!(image/20.png)


-Предположим, что в файле  text.txt записаны строки, показанные среди вариантов ответа. Отметьте только те из них, которые выведет на экран команда  grep "world" text.txt.
-The beautifulworld is not enough; The "world" is not enough; world; The world is not enough; The beautiful-world is not enough
!(image/21.png)


-Cкачайте архив с произведениями Шекспира. Вам нужно сгенерировать файл, в котором будут все строчки из этих произведений, содержащие “love”, и загрузить этот файл в форму.
-Whom whilst I laboured of a love to see,
LUCIANA. Ere I learn love, I'll practise to obey.
Would that alone a love he would detain,
As you love strokes, so jest with me again.
Your sauciness will jest upon my love,
For know, my love, as easy mayst thou fall...

!(image/22.png)

 

## Результаты

В ходе лабораторной работы приобрела простейшие навыки разработки, анализа, тестирования и отладки приложений в ОС типа UNIX/Linux на примере создания на языке программирования С калькулятора с простейшими функциями
