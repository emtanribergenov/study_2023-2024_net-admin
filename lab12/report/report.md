---
## Front matter
title: "Отчёт по лабораторной работе №12"
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

Приобретение практических навыков по настройке доступа локальной сети к внешней сети посредством NAT.


# Задание

1. Сделать первоначальную настройку маршрутизатора provider-gw-1 и коммутатора provider-sw-1 провайдера: задать имя, настроить доступ по паролю и т.п..
2. Настроить интерфейсы маршрутизатора provider-gw-1 и коммутатора provider-sw-1 провайдера.
3. Настроить интерфейсы маршрутизатора сети «Донская» для доступа к сети провайдера.
4. Настроить на маршрутизаторе сети «Донская» NAT.
5. Настроить доступ из внешней сети в локальную сеть организации.
6. Проверить работоспособность заданных настроек.




# Выполнение лабораторной работы


1. Сделал первоначальную настройку маршрутизатора (рис. [-@fig:001]) и коммутатора provider-sw-1 провайдера (рис. [-@fig:002]): задал имя, настроил доступ по паролю и т.п..

![Первоначальная настройка маршрутизатора provider-etanribergenov-gw-1](../images/0.0.png){#fig:001}

![Первоначальная настройка коммутатора provider-etanribergenov-sw-1](../images/0.1.png){#fig:002}




2. Настроил интерфейсы маршрутизатора (рис. [-@fig:003] - [-@fig:004]) и коммутатора (рис. [-@fig:005]) провайдера.

![Настройка интерфейсов маршрутизатора provider-etanribergenov-gw-1](../images/1.0.0.png){#fig:003}

![Настройка интерфейсов маршрутизатора provider-etanribergenov-gw-1](../images/1.0.1.png){#fig:004}

![Настройка интерфейсов коммутатора provider-etanribergenov-sw-1](../images/1.1.png){#fig:005}




3. Настроил интерфейсы маршрутизатора сети «Донская» для доступа к сети провайдера.

![Настройка интерфейсов маршрутизатора msk-donskaya-etanribergenov-gw-1](../images/2.0.png){#fig:006}




4. Настроил на маршрутизаторе сети «Донская» NAT.

![Настройка пула адресов для NAT](../images/3.0.png){#fig:007}


Создал расширенный список управления доступом "main-pool" для NAT: создал правила для каждой сети.


Хосты из сети дисплейных классов имеют доступ только к сайтам, необходимым для учёбы (www.yandex-etanribergenov.ru (192.0.2.11), stud-etanribergenov.rudn.university (192.0.2.12)).

![Настройка списка доступа для сети дисплейных классов](../images/3.1.png){#fig:008}


Сеть кафедр работает только с образовательными сайтами (esystem-etanribergenov.pfur.ru (192.0.2.13)).

![Настройка списка доступа для сети кафедр](../images/3.2.0.png){#fig:009}


Сеть администрации имеет возможность работать только с сайтом университета (www.rudn-etanribergenov.ru (192.0.2.14)).

![Настройка списка доступа для сети администрации](../images/3.2.1.png){#fig:010}


В сети для других пользователей компьютер администратора имеет полный доступ в Интернет. Другие не имеют доступа.

![Настройка списка доступа для компьютеров администраторов](../images/3.3.png){#fig:011}


Настроил Port Address Translation (PAT):

![Настройка Port Address Translation (PAT)](../images/3.4.png){#fig:012}


Настроил интерфейсы для NAT:

![Настройка интерфейсов для NAT](../images/3.5.png){#fig:013}



5. Настроил доступ из внешней сети в локальную сеть организации.

![Настройка доступа к www-серверу из Интернета](../images/4.0.png){#fig:014}

![Настройка доступа к файловому серверу из Интернета](../images/4.1.png){#fig:015}

![Настройка доступа к почтовому серверу из Интернета](../images/4.2.png){#fig:016}

![Настройка доступа к компьютеру администратора из Интернета](../images/4.3.png){#fig:017}




6. Проверил работоспособность заданных настроек.


Сеть дисплейных классов:

![Проверка доступа к серверу www.yandex.ru из сети дисплейных классов](../images/5.0.png){#fig:018}

![Проверка доступа к серверу stud.rudn.university из сети дисплейных классов](../images/5.1.png){#fig:019}

![Проверка отсутствия доступа к серверу www.rudn.ru из сети дисплейных классов](../images/5.2.png){#fig:020}



Сеть кафедр:

![Проверка доступа к серверу esystem.pfur.ru из сети кафедр](../images/5.3.png){#fig:021}

![Проверка отсутствия доступа к серверу www.yandex.ru из сети кафедр](../images/5.4.png){#fig:022}



Сеть администрации:

![Проверка доступа к серверу www.rudn.ru из сети администрации](../images/5.5.png){#fig:023}

![Проверка отсутствия доступа к серверу www.rudn.ru из сети администрации](../images/5.6.png){#fig:024}



Компьютер администратора:

![Проверка доступа ко всем узлам в сети по любому протоколу с компьютера администратора](../images/5.7.png){#fig:025}



Проверка доступа к узлам локальной сети из Интернета (проверка работоспособности настроек NAT):

![Проверка доступа к www-серверу из Интернета](../images/5.8.png){#fig:026}

![Проверка доступа к файловому серверу по ftp из Интернета](../images/5.9.png){#fig:027}



# Ответы на контрольные вопросы

1. Принцип работы NAT заключается в том, чтобы осуществлять перевод частного локального IP-адреса в общедоступный глобальный IP-адрес и наоборот. Это необходимо для обеспечения доступа к Интернету локальным узлам, использующим частные адреса.
2. NAT настраивается на маршрутизаторе.
3. Да. Преобразования NAT источника или назначения могут применяться к любому интерфейсу или подинтерфейсу с IP-адресом (включая интерфейсы программы набора номера).
4. Пул IP NAT - это набор из одного или нескольких общедоступных IPv4-адресов, которые используются в маршрутизаторе NAT.
5. Статическое преобразование сетевых адресов (NAT) выполняет взаимно однозначное преобразование внутренних IP-адресов во внешние.





# Выводы

Я приобрёл практические навыки по настройке доступа локальной сети к внешней сети посредством NAT.
