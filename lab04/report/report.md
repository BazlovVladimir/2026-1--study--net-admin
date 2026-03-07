---
## Front matter
title: "Отчёт по лабораторной работе №4"
subtitle: "Первоначальное конфигурирование сети"
author: "Владимир Базлов"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true
toc-depth: 2
lof: true
lot: true
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
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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
  - \usepackage{float}
  - \floatplacement{figure}{H}
---

# Цель работы

Провести подготовительную работу по первоначальной настройке коммутаторов сети.

# Выполнение

## Построение и первоначальная настройка сети L1 в Cisco Packet Tracer

### Размещение оборудования и построение топологии

В логической рабочей области Cisco Packet Tracer размещены коммутаторы и оконечные устройства согласно схеме сети L1 (рис. 3.1).

В состав топологии вошли:

- Коммутаторы серии 2960-24TT:
  - msk-donskaya-vabazlov-sw-1
  - msk-donskaya-vabazlov-sw-2
  - msk-donskaya-vabazlov-sw-3
  - msk-donskaya-vabazlov-sw-4
  - msk-pavlovskaya-vabazlov-sw-1
- Рабочие станции (PC-PT)
- Серверы (Server-PT): web, file, mail

Соединение устройств выполнено через соответствующие интерфейсы FastEthernet с использованием медного прямого кабеля (Copper Straight-Through). Межкоммутаторные соединения и подключения оконечных устройств выполнены в соответствии со схемой.

![Топология сети L1](Screenshot_1.png){ #fig:006 width=85% }

### Первоначальная настройка коммутаторов

Настройка всех коммутаторов выполнена по типовой последовательности команд первоначальной конфигурации. Для каждого устройства изменены имя (hostname) и IP-адрес интерфейса VLAN 2 согласно плану адресации.

В качестве шлюза по умолчанию указан адрес 10.128.1.1. Настроены пароли на консоль и линии VTY, задан enable secret, включено шифрование паролей, создан локальный пользователь admin, настроено доменное имя donskaya.rudn.edu и сгенерированы RSA-ключи для организации удалённого доступа по SSH.

### Настройка msk-donskaya-vabazlov-sw-1

Интерфейсу VLAN 2 назначен IP-адрес 10.128.1.2 с маской 255.255.255.0. Интерфейс переведён в активное состояние командой no shutdown.

Выполнена настройка:
- line vty 0 4 — пароль cisco, login
- line console 0 — пароль cisco, login
- enable secret cisco
- service password-encryption
- username admin privilege 1 secret cisco
- ip domain-name donskaya.rudn.edu
- crypto key generate rsa
- transport input ssh

Конфигурация сохранена командой write memory.

![CLI коммутатора msk-donskaya-vabazlov-sw-1](Screenshot_2.png){ #fig:007 width=85% }

### Настройка msk-donskaya-vabazlov-sw-2

Интерфейсу VLAN 2 назначен IP-адрес 10.128.1.3 с маской 255.255.255.0. Интерфейс активирован.

Выполнена аналогичная типовая настройка параметров безопасности и удалённого доступа по SSH. После завершения конфигурация сохранена в энергонезависимой памяти.

![CLI коммутатора msk-donskaya-vabazlov-sw-2](Screenshot_3.png){ #fig:008 width=85% }

### Настройка msk-donskaya-vabazlov-sw-3

Интерфейсу VLAN 2 назначен IP-адрес 10.128.1.4 с маской 255.255.255.0. Интерфейс переведён в состояние up.

Выполнена настройка паролей, локального пользователя, доменного имени, генерация RSA-ключей и включён доступ по SSH на линиях VTY.

![CLI коммутатора msk-donskaya-vabazlov-sw-3](Screenshot_4.png){ #fig:009 width=85% }

### Настройка msk-donskaya-vabazlov-sw-4

Интерфейсу VLAN 2 назначен IP-адрес 10.128.1.5 с маской 255.255.255.0.

Реализована типовая конфигурация безопасности, включающая установку паролей, enable secret, шифрование паролей, создание пользователя admin, назначение доменного имени и генерацию RSA-ключей для SSH-доступа.

![CLI коммутатора msk-donskaya-vabazlov-sw-4](Screenshot_5.png){ #fig:010 width=85% }

### Настройка msk-pavlovskaya-vabazlov-sw-1

Интерфейсу VLAN 2 назначен IP-адрес 10.128.1.6 с маской 255.255.255.0.

Выполнена первоначальная настройка устройства по типовой схеме: задано имя коммутатора, настроен шлюз по умолчанию, установлены пароли, создан пользователь admin, включено шифрование паролей и активирован доступ по SSH.

![CLI коммутатора msk-pavlovskaya-vabazlov-sw-1](Screenshot_6.png){ #fig:011 width=85% }

# Контрольные вопросы

1. **При помощи каких команд можно посмотреть конфигурацию сетевого оборудования?**  

   Для просмотра текущей (рабочей) конфигурации сетевого оборудования Cisco используется команда:

   `show running-config`

   Она отображает активную конфигурацию, которая в данный момент загружена в оперативную память (RAM) устройства и используется системой.

   Дополнительно могут применяться команды:  
   - `show running-config interface <имя_интерфейса>` — вывод конфигурации конкретного интерфейса;  
   - `show ip interface brief` — краткая информация о состоянии интерфейсов и назначенных IP-адресах;  
   - `show version` — сведения о версии IOS и параметрах устройства.

2. **При помощи каких команд можно посмотреть стартовый конфигурационный файл оборудования?**  

   Для просмотра стартовой конфигурации, которая хранится в энергонезависимой памяти (NVRAM), используется команда:

   `show startup-config`

   Этот файл загружается при перезапуске устройства и определяет его начальные параметры работы.

   Сравнение команд:  
   - `show running-config` — отображает текущую конфигурацию (RAM);  
   - `show startup-config` — отображает сохранённую конфигурацию (NVRAM).

3. **При помощи каких команд можно экспортировать конфигурационный файл оборудования?**  

   Экспорт конфигурационного файла возможен на внешний сервер (TFTP, FTP, SCP). Наиболее распространённый способ — использование TFTP:

   `copy running-config tftp`  
   `copy startup-config tftp`

   После ввода команды указывается IP-адрес сервера и имя файла.

   Также возможно сохранение конфигурации во внутреннюю память устройства:

   `copy running-config flash`

   Экспорт позволяет создать резервную копию конфигурации для последующего восстановления.

4. **При помощи каких команд можно импортировать конфигурационный файл оборудования?**  

   Импорт конфигурации выполняется с внешнего сервера в память устройства:

   `copy tftp running-config`  
   `copy tftp startup-config`

   После ввода команды указывается IP-адрес сервера и имя файла конфигурации.

   При загрузке в running-config параметры применяются немедленно.  
   При загрузке в startup-config изменения вступят в силу после перезагрузки устройства.

   Для применения стартовой конфигурации используется команда:

   `reload`

# Заключение

В Cisco Packet Tracer построена сеть уровня L1 в соответствии со схемой. Все коммутаторы получили уникальные имена и IP-адреса согласно плану адресации.

Настроены базовые механизмы защиты доступа и реализован удалённый доступ по протоколу SSH. Конфигурация каждого устройства сохранена в энергонезависимой памяти.
