---
lang: ru-RU
title: Лабораторная работа №8
subtitle: Настройка сетевых сервисов DHCP и DNS
author:
  - Владимир Базлов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 28 марта 2026

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

Приобретение практических навыков настройки  
DHCP и DNS в локальной сети Cisco Packet Tracer

# Настройка DNS-сервера

## Топология сети

![Схема сети](Screenshot_1.png){ width=70% }

## IP-настройка сервера

![IP DNS](Screenshot_2.png){ width=70% }

## DNS-записи

![DNS Records](Screenshot_3.png){ width=70% }

# Настройка DHCP

## Конфигурация маршрутизатора

![DHCP CLI](Screenshot_4.png){ width=70% }

## Пулы адресов

- dk — 10.128.3.0/24  
- departments — 10.128.4.0/24  
- adm — 10.128.5.0/24  
- other — 10.128.6.0/24  

## Проверка DHCP

![DHCP pool](Screenshot_5.png){ width=70% }

## Таблица привязок

![DHCP binding](Screenshot_6.png){ width=70% }

# Получение адресов

## DHCP на клиенте

![DHCP client](Screenshot_7.png){ width=70% }

## Проверка связи

![Ping](Screenshot_8.png){ width=70% }

# Работа DHCP (Simulation)

## Передача пакетов

![Simulation](Screenshot_9.png){ width=70% }

## DHCP Discover

![Discover](Screenshot_10.png){ width=70% }

## DHCP Offer

![Offer](Screenshot_11.png){ width=70% }

## DHCP Request

![Request](Screenshot_12.png){ width=70% }

## DHCP ACK

![ACK](Screenshot_13.png){ width=70% }

# Итоги работы

## Вывод

- настроен DNS-сервер  
- реализовано разрешение имён  
- настроен DHCP для нескольких подсетей  
- проверена автоматическая выдача адресов  
- исследован процесс DHCP в Simulation  

Получены навыки настройки сетевых сервисов  
и анализа работы протоколов DHCP и DNS