---
description: 'Цикл 21, Тема 122:BGP'
---

# Лабораторная по теме 122

{% file src="../../.gitbook/assets/lab122.zip" caption="Начальная конфигурация" %}

1. Загрузить начальную конфигурацию всех устройств.
2. Для задания используется логическая и физическая топологии проекта.
3. На маршрутизаторах R1, R2 настроить OSPF процесс 100 в Аrea 12, на следующих интерфейсах:
   1. R1- E0/1.12, Интерфейс Loopback0
   2. R2- E0/1.12, Интерфейс Loopback0
4. На маршрутизаторах R2, R3 настроить OSPF процесс 100 в Аrea 23, на следующих интерфейсах:
   1. R2- E0/1.23
   2. R3- E0/1.23
5. На маршрутизаторах R4, R6, R7 настроить OSPF процесс 100 в Аrea 764 на следующих интерфейсах:
   1. R4 — E0/1.456, Интерфейс Loopback0
   2. R6 — E0/1.456, E0/1.67, Интерфейс Loopback0
   3. R7 — E0/1.67, Интерфейс Loopback0
6. На маршрутизаторах R8,R9,R10 настроить OSPF процесс 100 в Аrea 108, на следующих интерфейсах:
   1. R8- E0/1.78, E0/1.89,Интерфейс Loopback0
   2. R9- E0/1.89, Интерфейс Loopback0, Интерфейс Multilink1
   3. R10- Интерфейс Loopback0, Интерфейс Multilink1
7. На маршрутизаторе R3 настроить BGP процесс следующим образом:
   1. Номер AS — 3
   2. Создать внешнюю bgp сессию следующим образом:
      1. Указать в качестве Remote AS номер 764
      2. Указать в качестве Update Source интерфейс Loopback0
      3. Позволить увеличение значения TTL только до 2 хопов
      4. Применить к маршрутизатору R4, указав IP адрес Loopback интерфейса
8. На маршрутизаторе R3 настроить статический маршрут к IP адресу интерфейса Loopback 0 маршрутизатора R4. В качестве Next Hop указать IP адрес интерфейса E0/1.34
9. На маршрутизаторе R1 настроить BGP процесс следующим образом:
   1. Номер AS — 21
   2. Создать внутренюю bgp сессию следующим образом:
      1. Создать BGP Peer Group:
         1. Название IBGP
         2. Указать в качестве Update Source интерфейс Loopback0
         3. В качестве соседа указать IP адрес Loopback интерфейса маршрутизатора R2
         4. Настроить марщрутизатор таким образом, чтобы он менял атрибут BGP NEXT\_HOP на свой собственный Loopback адрес.
10. На маршрутизаторе R2 настроить BGP процесс следующим образом:
    1. Номер AS — 21
    2. Редистрибьютить маршруты из OSPF 100 c метрикой 20
    3. Создать внутренюю bgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название IBGP
          2. Указать в качестве Update Source интерфейс Loopback0
          3. В качестве соседа указать IP адрес Loopback интерфейса маршрутизатора R1
          4. Настроить марщрутизатор таким образом, чтобы он менял атрибут BGP NEXT\_HOP на свой собственный Loopback адрес.
    4. Создать внешнюю ebgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название EBGP
          2. Позволить увеличение значения TTL только до 2 хопов
          3. Указать в качестве Update Source интерфейс Tunnel0
          4. В качестве соседа указать IP адрес Tunnel0 интерфейса маршрутизатора R7
11. На маршрутизаторе R5 настроить BGP процесс следующим образом:
    1. Номер AS — 5
    2. Создать внешнюю bgp сессию следующим образом:
       1. Указать в качестве Remote AS номер 764
       2. Указать в качестве Update Source интерфейс Loopback0
       3. Позволить увеличение значения TTL только до 2 хопов
       4. Применить к маршрутизатору R6, указав IP адрес Loopback интерфейса
12. На маршрутизаторе R5 настроить статический маршрут к IP адресу интерфейса Loopback 0 маршрутизатора R6. В качестве Next Hop указать IP адрес интерфейса E0/1.456
13. На маршрутизаторе R6 настроить статический маршрут к IP адресу интерфейса Loopback 0 маршрутизатора R5. В качестве Next Hop указать IP адрес интерфейса E0/1.456
14. На маршрутизаторе R4 настроить BGP процесс следующим образом:
    1. Номер AS — 764
    2. Редистрибьютить статический маршрут с мерикой 10
    3. Создать внутренюю bgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название IBGP
          2. Указать в качестве Update Source интерфейс Loopback0
          3. В качестве соседа указать IP адрес Loopback интерфейса маршрутизатора R6
          4. Настроить марщрутизатор таким образом, чтобы он менял атрибут BGP NEXT\_HOP на свой собственный Loopback адрес.
       2. Указать в качестве Update Source интерфейс Tunnel0
       3. В качестве соседа указать IP адрес Tunnel0 интерфейса маршрутизатора R7
    4. Создать внешнюю ebgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название EBGP
          2. Указать в качестве Update Source интерфейс Loopback0
          3. Позволить увеличение значения TTL только до 2 хопов
          4. В качестве соседей указать IP адрес Loopback интерфейса маршрутизаторов R3
15. На маршрутизаторе R6 настроить BGP процесс следующим образом:
    1. Номер AS — 764
    2. Редистрибьютить статический маршрут с метрикой 10
    3. Создать внутренюю bgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название IBGP
          2. Указать в качестве Update Source интерфейс Loopback0
          3. В качестве соседа указать IP адрес Loopback интерфейса маршрутизатора R4
          4. Настроить марщрутизатор таким образом, чтобы он менял атрибут BGP NEXT\_HOP на свой собственный Loopback адрес.
       2. Указать в качестве Update Source интерфейс Tunnel0
       3. В качестве соседа указать IP адрес Tunnel0 интерфейса маршрутизатора R7
    4. Создать внешнюю ebgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название EBGP
          2. Указать в качестве Update Source интерфейс Loopback0
          3. Позволить увеличение значения TTL только до 2 хопов
          4. В качестве соседа указать IP адрес Loopback интерфейса маршрутизатора R5
16. На маршрутизаторе R7 настроить BGP процесс следующим образом:
    1. Номер AS — 764
    2. Создать внутренюю bgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название IBGP
          2. Настроить марщрутизатор таким образом, чтобы он менял атрибут BGP NEXT\_HOP на свой собственный Loopback адрес.
       2. Указать в качестве Update Source интерфейс Tunnel0
       3. В качестве соседей указать IP адрес Tunnel0 интерфейса маршрутизатора R4, R6
    3. Создать внешнюю ebgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название EBGP
          2. Указать в качестве Update Source интерфейс Loopback0
          3. Позволить увеличение значения TTL только до 2 хопов
          4. В качестве соседей указать IP адрес Loopback интерфейса маршрутизаторов R8
          5. Указать в качестве Update Source интерфейс Tunnel0
          6. В качестве соседей указать IP адрес Tunnel0 интерфейса маршрутизатора R2
17. На маршрутизаторе R8 настроить BGP процесс следующим образом:
    1. Номер AS — 108
    2. Редистрибьютить OSPF процесс 100 с метрикой 20
    3. Создать ibgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название IBGP
          2. Указать в качестве Update Source интерфейс Loopback0
          3. В качестве соседа указать IP адрес Loopback интерфейсов маршрутизатора R9
    4. Создать внешнюю ebgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название EBGP
          2. Указать в качестве Update Source интерфейс Loopback0
          3. Позволить увеличение значения TTL только до 2 хопов
          4. В качестве соседей указать IP адрес Loopback интерфейса маршрутизаторов R7
18. На маршрутизаторе R9 настроить BGP процесс следующим образом:
    1. Номер AS — 108
    2. Создать ibgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название IBGP
          2. Указать в качестве Update Source интерфейс Loopback0
          3. В качестве соседа указать IP адрес Loopback интерфейсов маршрутизаторов R8, R10
19. На маршрутизаторе R10 настроить BGP процесс следующим образом:
    1. Номер AS — 108
    2. Создать ibgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название IBGP
          2. Указать в качестве Update Source интерфейс Loopback0
          3. В качестве соседа указать IP адрес Loopback интерфейсов маршрутизаторов R9
20. На маршрутизаторе R7 настроить статические маршруты к IP адресу интерфейса Loopback 0 маршрутизатора R8. В качестве Next Hop указать IP адреса интерфейса E0/1.78
21. На маршрутизаторе R8 настроить статические маршруты к IP адресу интерфейса Loopback 0 маршрутизатора R7. В качестве Next Hop указать IP адреса интерфейса E0/1.78
22. На маршрутизаторе R6 настроить статический маршрут к IP адресу интерфейса Loopback 0 маршрутизатора R5. В качестве Next Hop указать IP адреса интерфейса E0/1.456
23. Настроить DMVPN Phase 3 следующим образом:
    1. Настроить маршрутизатор R7 в качестве хаба DMVPN:
       1. Настроить интерфейс Tunnel0:
          1. IP адрес — 188.1.100.7/24
          2. Аутентификация NHRP — STANDARD
          3. Настроить динамическую поддержку мультикаста
          4. NHRP ID — 100
          5. Настроить NHRP Redirect
          6. Источник — интерфейс Ethernet 0/1.144
          7. Режим — GRE Multipoint
          8. Ключ туннеля 10000
    2. Настроить маршрутизаторы R2, R4, R6 качеcтве Spok’ов:
       1. Настроить интерфейс Tunnel0:
          1. IP адрес — использовать Overlay адрес топологии
          2. Аутентификация NHRP — STANDARD
          3. Настроить маппинг мультикаста к R7
          4. NHRP ID — 100
          5. В качестве сервера NHRP NHS указать R7
          6. Настроить NHRP Shortcut
          7. Источник — интерфейс Ethernet 0/1.144
          8. Режим — GRE Multipoint
          9. Ключ туннеля 10000
24. На маршрутизаторах R4, R6, R7 настроить Named mode EIGRP следующим образом:
    1. Имя Tunnel
    2. Номер процесса 72
    3. Следующие интерфейсы устройств должны участвовать в процессе:
       1. R2 — Интерфейс Tunnel 0
       2. R4- Интерфейс Tunnel 0
       3. R6 — Интерфейс Tunnel 0
       4. R7 — Интерфейс Tunnel 0
