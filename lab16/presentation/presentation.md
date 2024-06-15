---
## Front matter
lang: ru-RU
title: "Лабораторная работа № 16"
subtitle: "Настройка VPN"
author:
  - "Танрибергенов Эльдар"
institute:
  - "Российский университет дружбы народов, Москва, Россия"
date: 2024 г.

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
---


# Цели и задачи

## Цель лабораторной работы

Получение навыков настройки VPN-туннеля через незащищённое Интернет-соединение.



## Задачи

Настроить VPN-туннель между сетью Университета г. Пиза (Италия) и сетью «Донская» в г. Москва



# Выполнение работы

## Размещение в рабочей области проекта в соответствии с модельными предположениями оборудования для сети Университета г. Пиза

![Размещение оборудования в дополнительной площадке "Pisa, unipi"](../images/0.0.png){#fig:001 width=75% height=75%}



## Создание города Pisa и здания университета Unipi в нём 

![Создание города Pisa в физ. рабочей области](../images/2.0.png){#fig:002 width=75% height=75%}


## Создание города Pisa и здания университета Unipi в нём

![Создание здания Unipi в городе Pisa в физ. рабочей области](../images/2.1.png){#fig:003 width=75% height=75%}



## Перемещение соответсвующего оборудования в Pisa, Unipi

![Размещение оборудования в Pisa, unipi](../images/2.4.png){#fig:004 width=75% height=75%}



## Первоначальная настройка оборудования сети Университета г. Пиза

![Первоначальная настройка маршрутизатора pisa-unipi-etanribergenov-gw-1](../images/3.0.png){#fig:005 width=75% height=75%}


## Первоначальная настройка оборудования сети Университета г. Пиза

![Первоначальная настройка коммутатора pisa-unipi-etanribergenov-sw-1](../images/3.1.png){#fig:006 width=75% height=75%}


## Настройка интерфейсов оборудования сети Университета г. Пиза

![Настройка интерфейсов маршрутизатора pisa-unipi-etanribergenov-gw-1](../images/3.2.png){#fig:007 width=75% height=75%}

## Настройка интерфейсов оборудования сети Университета г. Пиза

![Настройка интерфейсов маршрутизатора pisa-unipi-etanribergenov-gw-1](../images/3.3.png){#fig:008 width=75% height=75%}


## Настройка интерфейсов оборудования сети Университета г. Пиза

![Настройка интерфейсов коммутатора pisa-unipi-etanribergenov-sw-1](../images/3.4.png){#fig:009 width=75% height=75%}


## Настройка интерфейсов оборудования сети Университета г. Пиза

![Настройка интерфейсов коммутатора pisa-unipi-etanribergenov-sw-1](../images/3.5.png){#fig:010 width=75% height=75%}


## Настройка узла pc-unipi-etanribergenov-1 сети Университета г. Пиза

![Настройка узла pc-unipi-etanribergenov-1: шлюз по умолчанию](../images/3.6.png){#fig:011 width=75% height=75%}

## Настройка узла pc-unipi-etanribergenov-1 сети Университета г. Пиза

![Настройка узла pc-unipi-etanribergenov-1: ip-адрес и маска устройства](../images/3.7.png){#fig:012 width=75% height=75%}




## Настройка VPN на основе протокола GRE

![Настройка маршрутизатора msk-donskaya-etanribergenov-gw-1](../images/4.0.png){#fig:013 width=75% height=75%}


## Настройка VPN на основе протокола GRE

![Настройка маршрутизатора pisa-unipi-etanribergenov-gw-1](../images/5.0.png){#fig:014 width=75% height=75%}




## Проверка доступности узлов сети Университета г. Пиза с ноутбука администратора сети «Донская»

![Проверка доступности узла pc-unipi-etanribergenov-1 c ноутбука администратора сети «Донская»](../images/6.0.png){#fig:015 width=75% height=75%}




# Результаты



## Результат

- Добавлена новая площадка - Университет в г. Пиза (Pisa, Unipi)
- Добавлены и настроены устройства в новой площадке
- Настроена VPN на основе протокола GRE





# Вывод

## Вывод

Я приобрёл практические навыки по настройке VPN-туннеля через незащищённое Интернет-соединение.