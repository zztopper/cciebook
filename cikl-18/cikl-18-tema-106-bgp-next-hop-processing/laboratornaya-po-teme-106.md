---
description: 'Цикл 18, Тема 106: BGP Next Hop Processing'
---

# Лабораторная по теме 106

{% file src="../../.gitbook/assets/lab106.zip" caption="Начальная конфигурация" %}

1. Загрузить начальную конфигурацию всех устройств.
2. Для задания используется логическая и физическая топологии проекта.
3. На маршрутизаторах R1, R2, R3, R5 настроить OSPF процесс 100 в Аrea 104 на всех интерфейсах:
   1. указать в качестве пассивных:
      1. R3- интерфейс E0/1.34
      2. R5- интерфейс E0/1.456
4. На маршрутизаторе R4 настроить OSPF процесс 100 в Аrea 4 на всех интерфейсах. Указать качестве пассивных:
   1. интерфейс E0/1.34
   2. интерфейс E0/1.456
5. На маршрутизаторах R6, R7, R8, R9, R10 настроить OSPF процесс 100 в Аrea 107 на всех интерфейсах:
   1. указать в качестве пассивных:
      1. интерфейс E0/1.456
6. На маршрутизаторах R1, R2, R3, R5 настроить внутренний и внешний BGP процесс следующим образом:
   1. Настроить внутренний bgp процесс:
      1. Номер AS — 51
      2. Создать bgp сессию следующим образом:
         1. Указать в качестве Remote AS номер 51
         2. Указать в качестве соседей IP адреса интерфейсов Loopback 0
         3. Настроить интервал задержки информирования BGP об изменениях в RIB в 6 секунд
         4. На R3 и R5 настроить команду, при которой все Next Hop адреса узнаются через OSPF
   2. Настроить внешний bgp процесс на R3 и R5:
      1. Номер AS — 51
      2. Создать bgp сессию следующим образом:
         1. Указать в качестве Remote AS номер 104
         2. Указать в качестве соседей IP адреса интерфейсов Loopback 0
         3. Настроить интервал задержки информирования BGP об изменениях в RIB в 6 секунд
         4. Позволить увеличение значения TTL только до 2 хопов
   3. На маршрутизаторе R4 настроить Confederation BGP процесс следующим образом:
   4. Номер AS — 4
   5. Создать внешнюю bgp сессию на R4 следующим образом:
      1. Указать в качестве идентификатора конфедерации номер AS 104
      2. Указать в качестве пира конфедерации 106
      3. Настроить Peer Group под названием EXTERNAL:
         1. Указать в качестве Remote AS номер 51
         2. Позволить увеличение значения TTL только до 2 хопов
         3. Указать в качестве соседей IP адреса интерфейсов Loopback 0
         4. Включить в группу маршрутизаторы R3 и R5
      4. Настроить Peer Group под названием CONF:
         1. Указать в качестве Remote AS номер 106
         2. Позволить увеличение значения TTL только до 2 хопов
         3. Указать в качестве соседей IP адреса интерфейсов Loopback 0
         4. Включить в группу маршрутизатор R6
7. Создать внешнюю bgp сессии на R6 следующим образом:
   1. Указать в качестве Remote AS номер
   2. Указать в качестве идентификатора конфедерации номер AS 104
   3. Позволить увеличение значения TTL только до 2 хопов
   4. Указать в качестве соседа IP адрес интерфейсов Loopback 0 маршрутизатора R4
   5. Создать внутренюю bgp сессию на R6 следующим образом:
      1. Указать в качестве Remote AS номер 106
      2. Указать в качестве соседей IP адреса интерфейсов Loopback
      3. Настроить команду, при которой все Next Hop адреса узнаются через OSPF
      4. Указать в качестве соседа IP адрес интерфейс Loopback 0 маршрутизатора R7
8. На маршрутизаторах R7, R8, R9, R10 настроить внутренний BGP процесс следующим образом:
   1. Номер AS — 106
   2. Настроить интервал задержки информирования BGP об изменениях в RIB в 6 секунд
   3. Настроить Peer Group под названием LOCAL:
      1. Указать в качестве Remote AS номер 106
      2. Указать в качестве соседей IP адреса интерфейсов Loopback 0
      3. Включить в группу:
         1. На R7 маршрутизаторы R6 и R8
         2. На R8 маршрутизаторы R7 и R9
         3. На R9 маршрутизаторы R8 и R10
         4. На R10 маршрутизатор R9
9. На маршрутизаторах R3 и R4 настроить статические маршруты к друг другу следующим образом:
   1. В качестве маршрута указать IP адрес Loopback0 интерфейса друг друга
   2. В качестве Next Hop указать IP адрес интерфейса E0/1.34 друг друга.
10. На маршрутизаторах R4 и R5 настроить статические маршруты к друг другу следующим образом:
    1. В качестве маршрута указать IP адрес Loopback0 интерфейса друг друга
    2. В качестве Next Hop указать IP адрес интерфейса E0/1.456 друг друга.
11. На маршрутизаторах R4 и R6 настроить статические маршруты к друг другу следующим образом:
    1. В качестве маршрута указать IP адрес Loopback0 интерфейса друг друга
    2. В качестве Next Hop указать IP адрес интерфейса E0/1.456 друг друга

{% file src="../../.gitbook/assets/lab106\_answers.zip" caption="Конечная конфигурация" %}

