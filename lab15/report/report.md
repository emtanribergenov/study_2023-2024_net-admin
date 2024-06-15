---
## Front matter
title: "Отчёт по лабораторной работе №15"
subtitle: "Дисциплина: Администрирование локальных сетей"
author: "Выполнил: Танрибергенов Эльдар"

## Generic options
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: ../bib/cite.bib
csl: ../pandoc/csl/gost-r-7-0-5-2008-numeric.csl

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

Настроить динамическую маршрутизацию между территориями организации.



# Задание

1. Настроить динамическую маршрутизацию по протоколу OSPF на маршрутизаторах msk-donskaya-gw-1, msk-q42-gw-1, msk-hostel-gw-1, sch-sochi-gw-1.
2. Настроить связь сети квартала 42 в Москве с сетью филиала в г. Сочи напрямую.
3. В режиме симуляции отследить движение пакета ICMP с ноутбука администратора сети на Донской в Москве (Laptop-PT admin) до компьютера пользователя в филиале в г. Сочи pc-sochi-1.
4. На коммутаторе провайдера отключить временно vlan 6 и в режиме симуляции убедиться в изменении маршрута прохождения пакета ICMP с ноутбука администратора сети на Донской в Москве (Laptop-PT admin) до компьютера пользователя в филиале в г. Сочи pc-sochi-1.
5. На коммутаторе провайдера восстановить vlan 6 и в режиме симуляции убедиться в изменении маршрута прохождения пакета ICMP с ноутбука администратора сети на Донской в Москве (Laptop-PT admin) до компьютера пользователя в филиале в г. Сочи pc-sochi-1.



# Выполнение лабораторной работы


1. Настроил динамическую маршрутизацию по протоколу OSPF на маршрутизаторах.

Включение OSPF на маршрутизаторе предполагает, во-первых, включение процесса OSPF командой router ospf \<process-id\>, 
во-вторых - назначение областей (зон) интерфейсам с помощью команды network \<network or IP address\> \<mask\> area \<area-id\>

![Настройка маршрутизатора msk-donskaya-etanribergenov-gw-1](../images/1.0.png){#fig:001}

Идентификатор процесса OSPF (process-id) по сути идентифицирует маршрутизатор в автономной системе, и, вообще говоря, он не должен совпадать с идентификаторами процессов на других маршрутизаторах.

Значение идентификатора области (area-id) может быть целым числом от 0 до 4294967295 или может быть представлено в виде IP-адреса: A.B.C.D.
Область 0 называется магистралью, области с другими идентификаторами должны подключаться к магистрали.


Проверил состояние протокола OSPF на маршрутизаторе msk-donskaya-gw-1:

![Статус протокола OSPF на маршрутизаторе](../images/1.1.png){#fig:002}

![Статус всех соседей в сегменте](../images/1.2.png){#fig:003}

![Информация из таблицы маршрутизации](../images/1.3.png){#fig:004}

Маршрутизаторы с общим сегментом являются соседями в этом сегменте. Соседи выбираются с помощью протокола Hello.
Команда show ip ospf neighbor показывает статус всех соседей в заданном сегменте.
Команда show ip ospf route (или show ip route) выводит информацию из таблицы маршрутизации.


![Настройка маршрутизатора msk-q42-etanribergenov-gw-1](../images/2.0.png){#fig:005}

![Настройка маршрутизирующего коммутатора msk-hostel-etanribergenov-gw-1](../images/2.1.png){#fig:006}

![Настройка маршрутизатора sch-sochi-etanribergenov-gw-1](../images/3.0.png){#fig:007}


Проверил состояние протокола OSPF на всех маршрутизаторах. У маршрутизаторов sch-sochi-... и msk-q42-... по одному соседу с одинаковым идентификатором, у msk-donskaya-... 2 соседа.


![Состояние протокола OSPF на маршрутизаторе sch-sochi-etanribergenov-gw-1](../images/4.0.png){#fig:008}

![Информация о соседях на маршрутизаторе sch-sochi-etanribergenov-gw-1](../images/4.1.png){#fig:009}

![Таблица маршрутизации на маршрутизаторе sch-sochi-etanribergenov-gw-1](../images/4.2.png){#fig:010}


![Состояние протокола OSPF на маршрутизаторе msk-q42-etanribergenov-gw-1](../images/4.3.png){#fig:011}

![Информация о соседях на маршрутизаторе msk-q42-etanribergenov-gw-1](../images/4.4.png){#fig:012}

![Таблица маршрутизации на маршрутизаторе msk-q42-etanribergenov-gw-1](../images/4.5.png){#fig:013}


![Состояние протокола OSPF на маршрутизаторе msk-donskaya-etanribergenov-gw-1](../images/4.6.png){#fig:014}

![Информация о соседях на маршрутизаторе msk-donskaya-etanribergenov-gw-1](../images/4.7.png){#fig:015}

![Таблица маршрутизации на маршрутизаторе msk-donskaya-etanribergenov-gw-1](../images/4.8.png){#fig:016}





2. Настроил связь сети квартала 42 в Москве с сетью филиала в г. Сочи напрямую.

![Настройка интерфейсов коммутатора provider-etanribergenov-sw-1](../images/5.0.png){#fig:017}

![Настройка маршрутизатора msk-q42-etanribergenov-gw-1](../images/5.1.png){#fig:018}

![Настройка коммутатора sch-sochi-etanribergenov-sw-1](../images/5.2.png){#fig:019}

![Настройка маршрутизатора sch-sochi-etanribergenov-gw-1](../images/5.3.png){#fig:020}



3. В режиме симуляции отследил движение пакета ICMP с ноутбука администратора сети на Донской в Москве до компьютера пользователя в филиале в г. Сочи pc-sochi-etanribergenov-1.

![Движение пакета ICMP с admin-etanribergenov до pc-sochi-etanribergenov](../images/6.0.png){#fig:021}

Пакет сначала доходит до маршрутизатора территории Сочи, а затем уже попадает на пк.

![Движение пакета ICMP с admin-etanribergenov до pc-sochi-etanribergenov](../images/6.1.png){#fig:022}

![Движение пакета ICMP с admin-etanribergenov до pc-sochi-etanribergenov](../images/6.2.png){#fig:023}



4. На коммутаторе провайдера отключил временно vlan 6 и в режиме симуляции убедился в изменении маршрута прохождения пакета ICMP с ноутбука администратора сети на Донской в Москве (Laptop-PT admin) до компьютера пользователя в филиале в г. Сочи pc-sochi-1.

![Выключение vlan 6 на коммутаторе провайдера](../images/7.0.png){#fig:024}

Теперь пакет приходит на маршрутизатор в 42 квартале в Москве, после чего направляется к целевому пк.

![Движение пакета ICMP с admin-etanribergenov до pc-sochi-etanribergenov по новому маршруту](../images/7.1.png){#fig:025}



5. На коммутаторе провайдера восстановил vlan 6 и в режиме симуляции убедился в изменении маршрута прохождения пакета ICMP с ноутбука администратора сети на Донской в Москве (Laptop-PT admin) до компьютера пользователя в филиале в г. Сочи pc-sochi-1.

![Включение vlan 6 на коммутаторе провайдера](../images/8.0.png){#fig:026}

Маршрут прохождения пакета ICMP снова перестроился. Пакет от коммутатора провайдера идёт напрямую к маршрутизатору в Сочи, а оттуда - к целевому пк.

![Движение пакета ICMP с admin-etanribergenov до pc-sochi-etanribergenov](../images/8.1.png){#fig:027}




# Ответы на контрольные вопросы

1.  RIP, RIPv2, IGRP, EIGRP, OSPF, Intermediate System-to-Intermediate System (IS-IS) - относятся к протоколам динамической маршрутизации.

2. Принцип работы протокола OSPF (Open Shortest Path First) заключается в следующем:
После включения маршрутизаторов протокол ищет непосредственно подключенных соседей и устанавливает с ними «дружеские» отношения.
Затем они обмениваются друг с другом информацией о подключенных и доступных им сетях, то есть строят карту сети (топологию сети).
На основе полученной информации запускается алгоритм SPF (Shortest Path First, «выбор наилучшего пути»), который рассчитывает оптимальный маршрут к каждой сети.

3. Маршрутизаторы периодически обмениваются специальной топологической информацией об имеющихся в интерсети сетях, а также о связях между маршрутизаторами. Обычно учитывается не только топология связей, но и их пропускная способность и состояние.

4. При просмотре таблицы маршрутизации отображается следующая информация:

- Адрес сети или узла назначения. Также может стоять маршрут по умолчанию.
- Маска сети назначения. С помощью маски указывается единичный адрес или же некоторый диапазон адресов.
- Шлюз, обозначающий адрес маршрутизатора в сети.
- Интерфейс, через который доступен шлюз.
- Метрика — числовой показатель, задающий предпочтительность маршрута.

# Выводы

Я приобрёл практические навыки по настройке динамической маршрутизации между территориями организации.
