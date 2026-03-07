---
## Front matter
title: "Отчёт по лабораторной работе №2"
subtitle: "Основы инфрмационной безопасности"
author: "Лисенков Е.Р."

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

# Цель работы

Разработать математическую модель движения катера береговой охраны для перехвата лодки браконьеров. Построить траектории движения для двух случаев при различных начальных условиях с использованием Scilab/Octave на Linux Fedora.

# Задачи

Постановка задачи

Катер береговой охраны обнаруживает лодку браконьеров на расстоянии k=6 км. Скорость катера в n=2 раза больше скорости лодки (v_катер = 2v_лодка). Лодка уходит прямолинейно под углом φ=135° (3π/4 рад).

Начальные условия:

    Полюс полярной системы — положение лодки в момент обнаружения (xₗ₀=(0,0))

    Катер находится на расстоянии k=6 км от полюса

    Два случая: r₀₁ = k/3 = 2 км (случай 1) и r₀₂ = k = 6 км (случай 2)


# Выполнение лабораторной работы

Этап 1: Установка Scilab на Fedora ([рис. @fig-001]).

![Установка](image/1.png){#fig-001 width=70%}


Этап 2: Подготовка скриптов

Создание файлов case1.m и case2.m с решением дифференциального уравнения и построением траекторий ([рис. @fig-002]):

![Подотовка скриптов](image/2.png){#fig-002 width=70%}

Этап 3: Проверка рабочего окружения

Убедился что всё установил ([рис. @fig-003])


![Проверка рабочего окружения](image/3.png){#fig-003 width=70%}


Этап 4: Запуск симуляции

Проверил запуск кода и отработку графиков ([рис. @fig-004]).

![Запуск](image/4.png){#fig-004 width=70%}


Этап 5: Полученные результаты

Получили готовые графики ([рис. @fig-005]).

![Результат](image/5.png){#fig-005 width=70%}


Полученные графики:

    Случай 1 (r₀=2 км, θ₀=0): Катер сразу начинает спиральное движение

    Случай 2 (r₀=6 км, θ₀=-π): Катер движется по логарифмической спирали

    Лодка браконьеров: Прямая линия под углом φ=135°


Анализ результатов

Точка пересечения траекторий (визуально определена на графиках):

    Случай 1: Пересечение происходит при r≈12-15 км, θ≈2.5-3 рад

    Случай 2: Пересечение при r≈20-25 км, θ≈1.8-2.2 рад (как в примере PDF)

Стратегия оптимальна: Катер нагоняет лодку, двигаясь по логарифмической спирали с постоянным угловым ускорением.


# Выводы

Разработана математическая модель задачи о погоне

Получены аналитические решения: r(θ) = r₀exp(θ/√3)

Построены траектории для n=2, k=6 км (оба случая)

Визуально определены точки перехвата

Программа работает стабильно на Linux Fedora с Octave

