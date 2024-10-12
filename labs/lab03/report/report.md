---
## Front matter
title: "Oтчёт по лабораторной работе"
subtitle: "№3"
author: "Хорошева Алёна Евгеньевна"

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
fontsize: 14pt
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

# Цель работы

Целью лабораторной работы является отчёт, оформленный с помощью языка разметки Markdown. Также редактирование с помощью vim и компиляция с использованием Makefile.

# Задание

1. В соответствующем каталоге сделайте отчёт по лабораторной работе № 2 в формате Markdown. В качестве отчёта необходимо предоставить отчёты в 3 форматах: pdf, docx и md.
2. Загрузите файлы на github.

# Теоретическое введение
**1. Базовые сведения о Markdown**
	Чтобы создать заголовок, используйте знак #, например:
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
	Чтобы задать для текста полужирное начертание, заключите его в двойные звездочки:
This text is **bold**.
	Чтобы задать для текста курсивное начертание, заключите его в одинарные звездочки:
This text is *italic*.
	Чтобы задать для текста полужирное и курсивное начертание, заключите его в тройные звездочки:
This is text is both ***bold and italic***.
	Блоки цитирования создаются с помощью символа >:
> The drought had lasted now for ten million years, and the reign of the
terrible lizards had long since ended. Here on the Equator, in the
continent which would one day be known as Africa, the battle for existence
had reached a new climax of ferocity, and the victor was not yet in sight.
In this barren and desiccated land, only the small or the swift or the
fierce could flourish, or even hope to survive.

	Упорядоченный список можно отформатировать с помощью соответствующих цифр:
1. First instruction
1. Sub-instruction
1. Sub-instruction
1. Second instruction
	Чтобы вложить один список в другой, добавьте отступ для элементов дочернего списка:
1. First instruction
	1. Second instruction
		1. Third instruction
	Неупорядоченный (маркированный) список можно отформатировать с помощью звездочек или тире:
* List item 1
* List item 2
* List item 3
	Чтобы вложить один список в другой, добавьте отступ для элементов дочернего списка:
- List item 1
	- List item A
	- List item B
- List item 2
	Синтаксис Markdown для встроенной ссылки состоит из части [link text], представляющей текст гиперссылки, и части (file-name.md) – URL-адреса или имени файла, на который дается ссылка:

Markdown поддерживает как встраивание фрагментов кода в предложение, так и их размещение между предложениями в виде отдельных огражденных блоков. Огражденные блоки кода — это простой способ выделить синтаксис для фрагментов кода. Общий формат огражденных блоков кода:
``` language
your code goes in here
```
3.2.2. Оформление формул в Markdown
	Внутритекстовые формулы делаются аналогично формулам LaTeX. Например, формула sin2(𝑥) + cos2(𝑥) = 1 запишется как $\sin^2 (x) + \cos^2 (x) = 1$
	Выключение формулы:
		sin2(𝑥) + cos2(𝑥) = 1 (3.1) со ссылкой в тексте «Смотри формулу ({-eq. 3.1}).» записывается как$$\sin^2 (x) + \cos^2 (x) = 1$$ {#eq:eq1}
Смотри формулу (`[-@eq:eq1]`).
**3.2.3. Оформление изображений в Markdown**
    В Markdown вставить изображение в документ можно с помощью непосредственного указания адреса изображения.
    Здесь:
• в квадратных скобках указывается подпись к изображению;
• в круглых скобках указывается URL-адрес или относительный путь изображения, а также (необязательно) всплывающую подсказку, заключённую в двойные или одиночные кавычки.
• в фигурных скобках указывается идентификатор изображения (#fig:fig1) для ссылки на него по тексту и размер изображения относительно ширины страницы (width=90)

Ссылка на изображение (рис. 3.1) может быть оформлена следующим образом (рис. [
@fig:fig1])

# Выполнение лабораторной работы

**Выполнение лабораторной работы**
1.Обновляю локальный репозиторий с помощью git pull
![](/home/alyona/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab03/report/image/1.png){}
2. В каталоге для отчёта текущей лабораторной работы использую команду make. Makefile находится в этом же каталоге report, поэтому файлы в docx и pdf форматах успешно сгенерировались. Проверяю наличие файлов в папке вручную.
![](/home/alyona/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab03/report/image/2.png){}
![](/home/alyona/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab03/report/image/3.png){}
3. Командой make clean удаляю файлы и проверяю, что их больше нет в папке report.
![](/home/alyona/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab03/report/image/4.png){}
![](/home/alyona/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab03/report/image/5.png){}
4. Открываю файл report.md с помощью редактора vim и начинаю заполнять отчёт по лабораторной работе согласно шаблону. 
![](/home/alyona/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab03/report/image/6.png){}
![](/home/alyona/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab03/report/image/7.png){}
![](/home/alyona/work/study/2024-2025/Архитектура компьютера/arch-pc/labs/lab03/report/image/8.png){}
# Выводы
**Вывод**

    По итогам лабораторной работы сформирован отчёт с использованием Markdown и текстового редактора vim.
Информация из теоретического введения помогла освоить навыки работы с Markdown:форматирование, вставка изображений, создание пронумерованных/маркированных списков и т.д.


# Список литературы{.unnumbered}

::: {#refs}
:::

