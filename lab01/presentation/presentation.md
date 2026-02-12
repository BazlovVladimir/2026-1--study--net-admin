---
lang: ru-RU
title: Лабораторная работа №1
subtitle: Знакомство с Cisco Packet Tracer
author:
  - Владимир Базлов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 10 февраля 2026

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

Изучить основы построения локальной сети в Cisco Packet Tracer  
и исследовать передачу данных между узлами.

# Построение сети с концентратором

## Создание топологии

![Схема сети с концентратором](Screenshot_1.png){ width=70% }

## Статические IP

![Настройка IP](Screenshot_2.png){ width=70% }

## Режим Simulation

![Передача пакетов](Screenshot_6.png){ width=70% }

## Наблюдение конфликта

![Коллизия](Screenshot_10.png){ width=70% }

# Построение сети с коммутатором

## Новая топология

![Сеть с коммутатором](Screenshot_12.png){ width=70% }

## Передача пакетов

![Передача через switch](Screenshot_17.png){ width=70% }

# Соединение Hub и Switch

## Передача между сегментами

![Соединение сегментов](Screenshot_20.png){ width=70% }

## Служебные пакеты

![STP пакет](Screenshot_23.png){ width=70% }

# Подключение маршрутизатора

## Настройка Router

![Маршрутизатор](Screenshot_24.png){ width=70% }

## Наблюдение протоколов

![CDP пакет](Screenshot_27.png){ width=70% }

# Итоги работы

## Вывод

В ходе лабораторной работы:

- построены сети с Hub и Switch;
- настроена IP-адресация;
- исследована передача ARP и ICMP;
- изучены коллизии и их причины;
- рассмотрены STP и CDP;
- подключён и настроен маршрутизатор.

Получены практические навыки анализа работы локальной сети и передачи данных.
