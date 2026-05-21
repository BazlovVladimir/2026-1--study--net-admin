---
lang: ru-RU
title: Лабораторная работа №15
subtitle: Динамическая маршрутизация
author:
  - Владимир Базлов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 16 мая 2026

toc: false
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цель работы

## Основная цель

Настроить динамическую маршрутизацию между территориями организации  
и проверить изменение маршрута при отказе одного из каналов связи.

# Топология сети

## Корпоративная сеть

![Общая схема корпоративной сети](Screenshot_1.png){ width=80% }

# Настройка OSPF

## Маршрутизатор msk-donskaya-gw-1

![Настройка OSPF на msk-donskaya-gw-1](Screenshot_2.png){ width=80% }

## Маршрутизатор msk-q42-gw-1

![Настройка OSPF на msk-q42-gw-1](Screenshot_3.png){ width=80% }

## Маршрутизатор msk-hostel-gw-1

![Настройка OSPF на msk-hostel-gw-1](Screenshot_4.png){ width=80% }

## Маршрутизатор sch-sochi-gw-1

![Настройка OSPF на sch-sochi-gw-1](Screenshot_5.png){ width=80% }

# Прямая связь q42 — Сочи

## Создание VLAN 7

![Создание VLAN 7 на коммутаторе провайдера](Screenshot_6.png){ width=80% }

## Настройка подинтерфейса q42

![Настройка подинтерфейса на msk-q42-gw-1](Screenshot_7.png){ width=80% }

## Настройка VLAN 7 в Сочи

![Создание VLAN 7 на коммутаторе филиала](Screenshot_8.png){ width=80% }

## Настройка подинтерфейса Сочи

![Настройка подинтерфейса на sch-sochi-gw-1](Screenshot_9.png){ width=80% }

# Проверка маршрутизации

## Проверка msk-donskaya-gw-1

![OSPF-соседи и таблица маршрутизации msk-donskaya-gw-1](Screenshot_10.png){ width=80% }

## Проверка msk-q42-gw-1

![OSPF-соседи и таблица маршрутизации msk-q42-gw-1](Screenshot_11.png){ width=80% }

## Проверка msk-hostel-gw-1

![OSPF-соседство и таблица маршрутизации msk-hostel-gw-1](Screenshot_12.png){ width=80% }

## Проверка sch-sochi-gw-1

![OSPF-соседи и таблица маршрутизации sch-sochi-gw-1](Screenshot_13.png){ width=80% }

# Проверка ICMP

## Основной маршрут

![Прохождение ICMP-пакета до компьютера в Сочи](Screenshot_14.png){ width=80% }

## Отключение VLAN 6

![Отключение интерфейса Vlan6](Screenshot_15.png){ width=80% }

## Изменение маршрута

![Изменение маршрута после отключения Vlan6](Screenshot_16.png){ width=80% }

## Восстановление VLAN 6

![Восстановление интерфейса Vlan6](Screenshot_17.png){ width=80% }

## Проверка после восстановления

![Прохождение ICMP-пакета после восстановления Vlan6](Screenshot_18.png){ width=80% }

# Итоги работы

## Вывод

В ходе лабораторной работы:

- настроен протокол OSPF на маршрутизаторах организации;
- создана прямая связь между сетью квартала 42 и филиалом в Сочи;
- настроена VLAN 7 и подинтерфейсы с инкапсуляцией 802.1Q;
- проверены OSPF-соседства и таблицы маршрутизации;
- исследовано прохождение ICMP-пакета в режиме Simulation;
- проверено изменение маршрута после отключения VLAN 6;
- восстановлен основной канал связи через VLAN 6.