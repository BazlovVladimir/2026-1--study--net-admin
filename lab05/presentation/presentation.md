---
lang: ru-RU
title: Лабораторная работа №5
subtitle: Конфигурирование VLAN
author:
  - Владимир Базлов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 08 марта 2026

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

Получить основные навыки по настройке VLAN на коммутаторах сети.

# Настройка IP-адресов

## Топология сети

![Топология сети в Cisco Packet Tracer](Screenshot_1.png){ width=70% }

## Настройка IP на ПК

![Настройка IP-адреса](Screenshot_2.png){ width=70% }

## Примеры адресации узлов

- dk-donskaya-vabazlov-1 — 10.128.3.5/24
- dk-pavlovskaya-vabazlov-1 — 10.128.3.10/24
- dep-donskaya-vabazlov-1 — 10.128.4.5/24
- adm-donskaya-vabazlov-1 — 10.128.5.5/24
- other-donskaya-vabazlov-1 — 10.128.6.5/24
- other-pavlovskaya-vabazlov-1 — 10.128.6.10/24

# Настройка VLAN и VTP

## VTP-сервер и создание VLAN

![Настройка VTP-сервера и создание VLAN](Screenshot_8.png){ width=70% }

## Созданные VLAN

- VLAN 2 — management
- VLAN 3 — servers
- VLAN 101 — dk
- VLAN 102 — departments
- VLAN 103 — adm
- VLAN 104 — other

## Настройка VTP-клиента

![Настройка VTP-клиента](Screenshot_9.png){ width=70% }

## Назначение VLAN на коммутаторах

- msk-pavlovskaya-sw-1:
  - Fa0/1–Fa0/15 → VLAN 101
  - Fa0/20 → VLAN 104
- msk-donskaya-sw-2:
  - Fa0/1–Fa0/2 → VLAN 3
- msk-donskaya-sw-3:
  - Fa0/1–Fa0/2 → VLAN 3
- msk-donskaya-sw-4:
  - Fa0/1–Fa0/5 → VLAN 101
  - Fa0/6–Fa0/10 → VLAN 102
  - Fa0/11–Fa0/15 → VLAN 103
  - Fa0/16–Fa0/20 → VLAN 104

# Настройка Trunk-портов

## Магистральные соединения

- На msk-donskaya-sw-1 trunk настроен на:
  - FastEthernet0/24
  - FastEthernet0/1
  - GigabitEthernet0/1
  - GigabitEthernet0/2

- На клиентских коммутаторах trunk используется для передачи нескольких VLAN между устройствами.

## Настройка VLAN на коммутаторе доступа

![Настройка VLAN на коммутаторе msk-donskaya-sw-4](Screenshot_12.png){ width=70% }

# Проверка связности

## Проверка ping внутри и между VLAN

![Проверка доступности устройств командой ping](Screenshot_13.png){ width=70% }

## Результаты проверки

- узлы из одной VLAN успешно обмениваются ICMP-пакетами;
- узлы из разных VLAN недоступны;
- межвлановая маршрутизация в данной топологии не настроена.

## Дополнительная проверка

![Проверка доступности устройств внутри VLAN](Screenshot_14.png){ width=70% }

# Анализ передачи ICMP

## Режим Simulation

![Передача пакета в режиме Simulation](Screenshot_15.png){ width=70% }

## Структура ICMP-запроса

![Структура ICMP-запроса](Screenshot_16.png){ width=70% }

## Структура ICMP-ответа

![Структура ICMP-ответа](Screenshot_17.png){ width=70% }

# Итоги работы

## Вывод

В ходе лабораторной работы:

- настроена топология сети в Cisco Packet Tracer;
- назначены статические IP-адреса узлам сети;
- создана база VLAN и выполнено именование виртуальных сетей;
- настроен VTP-сервер и VTP-клиенты;
- настроены trunk-порты на коммутаторах;
- проверена связность узлов с помощью ping;
- исследована передача ICMP-пакетов в режиме Simulation.

Получены практические навыки настройки VLAN, VTP и анализа сетевого трафика в локальной сети.