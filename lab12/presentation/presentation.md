---
lang: ru-RU
title: Лабораторная работа №12
subtitle: Настройка NAT
author:
  - Владимир Базлов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 25 апреля 2026

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

Изучить настройку доступа локальной сети к внешней сети  
с использованием технологии NAT.

# Настройка сети провайдера

## Маршрутизатор provider-gw-1

![Настройка маршрутизатора](Screenshot_1.png){ width=70% }

## Коммутатор provider-sw-1

![Настройка коммутатора](Screenshot_2.png){ width=70% }

# Подключение сети «Донская»

## Настройка маршрутизатора

![Подключение к провайдеру](Screenshot_3.png){ width=70% }


# Настройка NAT

## Динамический NAT

![Настройка NAT](Screenshot_4.png){ width=70% }

# Проверка доступа

## Дисплейные классы

![Доступ к Yandex](Screenshot_5.png){ width=70% }

## Дисплейные классы

![Доступ к stud.rudn](Screenshot_6.png){ width=70% }

## Дисплейные классы

![Блокировка](Screenshot_7.png){ width=70% }

## Кафедры и администрация

![Кафедры](Screenshot_8.png){ width=70% }

## Кафедры и администрация

![Администрация](Screenshot_9.png){ width=70% }

## Кафедры и администрация

![Администратор](Screenshot_10.png){ width=70% }

# Проверка внешнего доступа

## Внешний клиент

![IP настройка](Screenshot_11.png){ width=70% }

## WEB-сервер

![WEB доступ](Screenshot_12.png){ width=70% }

## FTP-сервер

![FTP доступ](Screenshot_13.png){ width=70% }

## Почтовый сервер

![Почта](Screenshot_14.png){ width=70% }

# Итоги работы

## Вывод

- настроен NAT (динамический и статический)  
- реализованы политики доступа  
- обеспечен выход в Интернет  
- настроен доступ извне к серверам  

Получены навыки настройки NAT и фильтрации трафика.