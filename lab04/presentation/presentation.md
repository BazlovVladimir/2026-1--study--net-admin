---
lang: ru-RU
title: Лабораторная работа №4
subtitle: Первоначальное конфигурирование сети
author:
  - Владимир Базлов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 28 февраля 2026

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

Провести подготовительную работу по первоначальной настройке  
коммутаторов сети в Cisco Packet Tracer.

# Построение сети L1

## Размещение оборудования

![Топология сети L1](Screenshot_1.png){ width=75% }

# Первоначальная настройка

## Типовая конфигурация

Для каждого коммутатора выполнены:

- назначение hostname  
- настройка интерфейса VLAN 2  
- назначение IP-адреса  
- указание шлюза по умолчанию  
- настройка паролей  
- создание пользователя admin  
- включение SSH  
- сохранение конфигурации  

## Настройка msk-donskaya-vabazlov-sw-1

![CLI sw-1](Screenshot_2.png){ width=80% }

## Настройка msk-donskaya-vabazlov-sw-2

![CLI sw-2](Screenshot_3.png){ width=80% }

## Настройка msk-donskaya-vabazlov-sw-3

![CLI sw-3](Screenshot_4.png){ width=80% }

## Настройка msk-donskaya-vabazlov-sw-4

![CLI sw-4](Screenshot_5.png){ width=80% }

## Настройка msk-pavlovskaya-vabazlov-sw-1

![CLI pavlovskaya-sw-1](Screenshot_6.png){ width=80% }

# Итоги работы

## Вывод

В ходе лабораторной работы:

- построена сеть L1;  
- выполнена базовая настройка коммутаторов;  
- назначены IP-адреса управления;  
- реализована защита доступа;  
- настроен удалённый доступ по SSH;  
- конфигурация сохранена в NVRAM.  

Сеть подготовлена к дальнейшему конфигурированию и тестированию.