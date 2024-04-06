---
## Front matter
title: "Отчёт по лабораторной работе №5"
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

Получить основные навыки по настройке VLAN на коммутаторах сети.


# Задание

1. На коммутаторах сети настроить Trunk-порты на соответствующих интерфейсах, связывающих коммутаторы между собой.
2. Коммутатор msk-donskaya-etanribergenov-sw-1 настроить как VTP-сервер и прописать на нём номера и названия VLAN.
3. Остальные коммутаторы настроить как VTP-клиенты, на интерфейсах указать принадлежность к соответствующему VLAN.
4. На серверах прописать IP-адреса.
5. На оконечных устройствах указать соответствующий адрес шлюза и прописать статические IP-адреса из диапазона соответствующей сети, следуя регламенту выделения ip-адресов из предыдущих ЛР.
6. Проверить доступность устройств, принадлежащих одному VLAN, и недоступность устройств, принадлежащих разным VLAN.
7. Используя режим симуляции в Packet Tracer, изучите процесс передвижения пакета ICMP по сети. Изучите содержимое передаваемого пакета и заголовки задействованных протоколов.

# Выполнение лабораторной работы


1. На коммутаторах сети на интерфейсах, связывающих коммутаторы между собой, перевёл режим работы портов в значение "Trunk"

![Конфигурация интерфейсов коммутатора msk-donskaya-etanribergenov-sw-1](../images/1.png){#fig:001}

![Конфигурация интерфейсов коммутатора msk-donskaya-etanribergenov-sw-2](../images/2.png){#fig:002}

![Конфигурация интерфейсов коммутатора msk-donskaya-etanribergenov-sw-3](../images/3.png){#fig:003}

![Конфигурация интерфейсов коммутатора msk-donskaya-etanribergenov-sw-4](../images/4.png){#fig:004}

![Конфигурация интерфейсов коммутатора msk-pavlovskaya-etanribergenov-sw-1](../images/5.png){#fig:005}



2. Коммутатор msk-donskaya-etanribergenov-sw-1 настроил как VTP-сервер и прописал на нём номера и названия VLAN.

![Настройка VTP-сервера и создание vlan](../images/6.png){#fig:006}



3. Остальные коммутаторы настроил как VTP-клиенты, на интерфейсах указал принадлежность к соответствующему VLAN.

Коммутатор msk-donskaya-etanribergenov-sw-4:

![Настройка VTP-клиента](../images/7.png){#fig:007}

![Указание интерфейсам принадлежность к VLAN](../images/8.png){#fig:008}

Проверка получения списка VLAN от VTP-сервера и установки принадлежности интерфейсов к соответствующим VLAN

![Сведения о VLAN](../images/9.png){#fig:009}



Коммутатор msk-donskaya-etanribergenov-sw-2:

![Настройка VTP-клиента](../images/10.png){#fig:010}

![Указание интерфейсам принадлежность к VLAN](../images/11.png){#fig:011}

Проверка получения списка VLAN от VTP-сервера и установки принадлежности интерфейсов к соответствующим VLAN

![Сведения о VLAN](../images/12.png){#fig:012}



Коммутатор msk-donskaya-etanribergenov-sw-3:

![Настройка VTP-клиента](../images/13.png){#fig:013}

![Указание интерфейсам принадлежность к VLAN](../images/14.png){#fig:014}

Проверка получения списка VLAN от VTP-сервера и установки принадлежности интерфейсов к соответствующим VLAN

![Сведения о VLAN](../images/15.png){#fig:015}



Коммутатор msk-pavlovskaya-etanribergenov-sw-1:

![Настройка VTP-клиента](../images/16.png){#fig:016}

![Указание интерфейсам принадлежность к VLAN](../images/17.png){#fig:017}

Проверка получения списка VLAN от VTP-сервера и установки принадлежности интерфейсов к соответствующим VLAN

![Сведения о VLAN](../images/18.png){#fig:018}



4. На серверах прописал IP-адреса.

![Сервер Web: шлюз](../images/19.png){#fig:019}

![Сервер Web: ip-адрес и маска](../images/20.png){#fig:020}


![Сервер File: шлюз](../images/21.png){#fig:021}

![Сервер File: ip-адрес и маска](../images/22.png){#fig:022}


![Сервер Mail: шлюз](../images/23.png){#fig:023}

![Сервер Mail: ip-адрес и маска](../images/24.png){#fig:024}



5. На оконечных устройствах указал соответствующий адрес шлюза и прописал статические IP-адреса из диапазона соответствующей сети, следуя регламенту выделения ip-адресов:

На территории "Москва, Павловская":

![Оконеч. у-во dk-pavlovskaya-etanribergenov: шлюз](../images/25.png){#fig:025}

![Оконеч. у-во dk-pavlovskaya-etanribergenov: ip-адрес и маска](../images/26.png){#fig:026}


![Оконеч. у-во other-pavlovskaya-etanribergenov: шлюз](../images/27.png){#fig:027}

![Оконеч. у-во other-pavlovskaya-etanribergenov: ip-адрес и маска](../images/28.png){#fig:028}



На территории "Москва, Донская":

![Оконеч. у-во dk-donskaya-etanribergenov: шлюз](../images/29.png){#fig:029}

![Оконеч. у-во dk-donskaya-etanribergenov: ip-адрес и маска](../images/30.png){#fig:030}


![Оконеч. у-во dep-donskaya-etanribergenov: шлюз](../images/31.png){#fig:031}

![Оконеч. у-во dep-donskaya-etanribergenov: ip-адрес и маска](../images/32.png){#fig:032}


![Оконеч. у-во adm-donskaya-etanribergenov: шлюз](../images/33.png){#fig:033}

![Оконеч. у-во adm-donskaya-etanribergenov: ip-адрес и маска](../images/34.png){#fig:034}


![Оконеч. у-во other-donskaya-etanribergenov: шлюз](../images/35.png){#fig:035}

![Оконеч. у-во other-donskaya-etanribergenov: ip-адрес и маска](../images/36.png){#fig:036}




6. Проверил доступность устройств, принадлежащих одному VLAN, и недоступность устройств, принадлежащих разным VLAN.

Использовал команду ping в Command Prompt:

Из одного VLAN:

![Пингование устр-ва из одного VLAN](../images/37.png){#fig:037}


Из разных VLAN:

![Пингование устр-ва из разных VLAN](../images/38.png){#fig:038}



7. Используя режим симуляции в Packet Tracer, изучил процесс передвижения пакета ICMP по сети.

![Отправка пакета устр-ву из одного VLAN](../images/39.png){#fig:039}


Изучил содержимое передаваемого пакета и заголовки задействованных протоколов.

![Кадр Ethernet](../images/40.png){#fig:040}

В кадре Ethernet добавились поля, указывающие тег.


Отправка пакета устройству из разных VLAN:

![Отправка пакета устр-ву из разных VLAN](../images/41.png){#fig:041}



# Ответы на контрольные вопросы

1. Команда *show vlan* используется для просмотра списка VLAN на сетевом устройстве.

2. VLAN Trunking Protocol (VTP) - это протокол передачи данных о VLAN. 
Команды: vtp mode \<server/client\> - переводит устройство в режим VTP-сервера/клиента;
vtp domain \<название\> - указание домена
vtp password \<пароль\> - установка пароля

3. Internet Control Message Protocol (ICMP) - сетевой протокол, входящий в стек протоколов TCP/IP.
В основном ICMP используется для передачи сообщений об ошибках и других исключительных ситуациях, возникших при передаче данных, например, запрашиваемая услуга недоступна или хост или маршрутизатор не отвечают. 
Также на ICMP возлагаются некоторые сервисные функции.
Формат пакета ICMP: Заголовок кадра Ethernet, заголовок IP, заголовок ICMP (тип, код, контрол.сумма), сообщение ICMP.

4. Address Resolution Protocol (ARP) - это сетевой протокол, предназначенный для определения MAC-адреса другого компьютера по известному IP-адресу.
Формат ARP-пакета: тип оборудования, тип протокола, MAC-адрес отправителя и получателя, IP-адрес отправителя и получателя.

5. MAC-адрес - это уникальный идентификатор, присвоенный сетевому адаптеру или сетевому интерфейсу устройства, подключённого к сети.
Он состоит из 6 шестнадцатеричных цифр (октетов), разделённых двоеточиями, и имеет длину 48 бит. 

# Выводы

Я получил основные навыки по настройке VLAN на коммутаторах сети.

