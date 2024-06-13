---
## Front matter
title: "Отчёт по лабораторной работе №11"
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

Провести подготовительные мероприятия по подключению локальной сети организации к Интернету.


# Задание

1. Построить схему подсоединения локальной сети к Интернету.
2. Построить модельные сети провайдера и сети Интернет.
3. Построить схемы сетей L1, L2, L3.




# Выполнение лабораторной работы



1. Внёс изменения в схему L1 сети, добавив в неё сеть провайдера и сеть модельного Интернета с указанием названий оборудования и портов подключения.

![Схема L1: вся сеть](../images/0.0.png){#fig:001}

![Схема L1: добавленные устройства](../images/0.1.png){#fig:002}




2. Внёс изменения в схемы L2 и L3 сети, указав адреса и VLAN сети провайдера и модельной сети Интернета.

![Схема L2: добавленные устройства](../images/1.0.png){#fig:003}

![Схема L3](../images/1.1.png){#fig:004}


 Скорректировал таблицы распределения IP-адресов и портов.

![Таблица распределения IP-адресов: добавленные устройства](../images/2.0.png){#fig:005}

![Таблица портов: добавленные устройства](../images/2.1.png){#fig:006}




3. На схеме предыдущего своего проекта разместил необходимое оборудование для сети провайдера и сети модельного Интернета: 
4 медиаконвертера (Repeater-PT), 2 коммутатора типа Cisco 2960-24TT, маршрутизатор типа Cisco 2811, 4 сервера.

![Размещение и частичное соединение устройств](../images/3.0.png){#fig:007}




4. В физической рабочей области добавил здание провайдера и здание, имитирующее расположение серверов модельного Интернета. Присвоил им соответствующие названия: Provider и Internet.

![Здания провайдера и модельной сети Интернета](../images/4.0.png){#fig:008}




5. Перенёс из сети «Донская» оборудование провайдера и модельной сети Интернета в соответствующие здания.

![Перенос сервера yandex в здание модельной сети Интернета](../images/5.0.png){#fig:009}

![Перенос коммутатора в здание провайдера](../images/5.1.png){#fig:010}

![Оборудование в здании провайдера](../images/5.2.png){#fig:011}

![Оборудование в здании модельной сети Интернета](../images/5.3.png){#fig:012}




6. На медиаконвертерах заменил имеющиеся модули на PT-REPEATER-NM-1FFE и PT-REPEATER-NM-1CFE для подключения витой пары по технологии Fast Ethernet и оптоволокна соответственно.

![Замена модулей на медиконвертере](../images/6.0.png){#fig:013}





7. Провёл соединение объектов согласно скорректированной схеме L1.

![Соединение после замены модулей](../images/7.0.png){#fig:014}




8. Прописал IP-адреса серверам:

![Адреса шлюза и DNS-сервера esystem.pfur.ru](../images/8.0.png){#fig:015}

![Адрес сервера esystem.pfur.ru](../images/8.1.png){#fig:016}

![Адреса шлюза и DNS-сервера rudn.ru](../images/8.2.png){#fig:017}

![Адрес сервера rudn.ru](../images/8.3.png){#fig:018}

![Адреса шлюза и DNS-сервера yandex.ru](../images/8.4.png){#fig:019}

![Адрес сервера yandex.ru](../images/8.5.png){#fig:020}

![Адреса шлюза и DNS-сервера stud.rudn.university](../images/8.6.png){#fig:021}

![Адрес сервера stud.rudn.university](../images/8.7.png){#fig:022}




9. Прописал сведения о серверах на DNS-сервере сети «Донская»:

![Добавление DNS-записи](../images/9.0.png){#fig:023}

![Список DNS-записей](../images/9.1.png){#fig:024}






# Ответы на контрольные вопросы


1. NAT (Network Address Translation) - механизм преобразования IP-адресов транзитных пакетов для обеспечения доступа устройств локальных сетей с внутренними IP-адресами к сети Интернет.

2. Проверить IP-адрес компьютера. Если он находится в одном из диапазонов, зарезервированных для локальных сетей, то это локальный (внутренний) адрес, и узел находится за NAT.

3. Маршрутизатор отвечает за преобразование адреса методом NAT.

4,5. 

- Статический NAT (Static NAT, SNAT) — осуществляет преобразование адресов по принципу 1:1 (в частности, один локальный IP-адрес преобразуется во внешний адрес, выделенный, например, провайдером);

- Динамический NAT (Dynamic NAT, DNAT) — осуществляет преобразование адресов по принципу 1:N (например, один адрес устройства локальной сети преобразуется в один из адресов диапазона внешних адресов);

- NAT Overload (или NAT Masquerading, или Port Address Translation, PAT) — осуществляет преобразование адресов по принципу N:1 (например, адреса группы устройств локальной подсети преобразуются в один внешний адрес, при этом дополнительно используется механизм адресации через номера портов).


# Выводы

Я научился проводить подготовительные мероприятия по подключению локальной сети организации к Интернету.
