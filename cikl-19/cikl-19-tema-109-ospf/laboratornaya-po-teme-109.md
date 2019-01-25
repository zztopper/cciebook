---
description: 'Цикл 19, Тема 109: OSPF'
---

# Лабораторная по теме 109

{% file src="../../.gitbook/assets/lab109.zip" caption="Начальная конфигурация" %}

1. Загрузить начальную конфигурацию всех устройств.
2. Для задания используется логическая и физическая топологии проекта.
3. На маршрутизаторах R1, R2, R3, R4, R5 настроить OSPF процесс 100 в Аrea 51 на следующих интерфейсах c типом сети Point-to-Point:
   1. R1 — E0/1.12, Loopback0
   2. R2- E0/1.12, Loopback0
   3. R3- E0/1.34, Loopback0
   4. R4- E0/1.34, Loopback0
   5. R5- E0/1.235,  Loopback0
4. На маршрутизаторах R2, R3, R5 настроить OSPF процесс 100 в Аrea 51 на следующих интерфейсах c типом сети Broadcast:
   1. R2 — E0/1.235, E0/1.23
   2. R3- E0/1.235, E0/1.23
   3. R5- E0/1.235
5. На маршрутизаторах R4, R5 настроить OSPF процесс 100 в Аrea 0 на следующих интерфейсах c типом сети Point-to-Point:
   1. R4- E0/1.456
   2. R5 — E0/1.456
   3. Настроить аутентификацию MD5 с паролем OSPF\_EXT
6. На маршрутизаторах R6, R7, R8, R9, R10 настроить OSPF процесс 107 в Аrea 76 на следующих интерфейсах:
   1. R6 — E0/1.67, Loopback0
   2. R7- E0/1.67, E0/1.78, Loopback0
   3. R8- E0/1.78, E0/1.89, Loopback0
   4. R9- E0/1.89, Multilink1, Loopback0
   5. R10- Multilink1, Loopback0
7. На маршрутизаторе R6 настроить следующие статические маршруты:
   1. Маршрут по-умолчанию 0.0.0.0/0, в качестве Next Hop указать интерфейс Null0
   2. Маршрут 180.1.4.4/32, в качестве Next Hop указать IP адрес интерфейса E0/1.456 маршрутизатора R4
8. На маршрутизаторе R4 настроить следующие статические маршруты:
   1. Маршрут 180.1.6.6/32, в качестве Next Hop указать IP адрес интерфейса E0/1.456 маршрутизатора R6
9. На маршрутизаторе R6 настроить внешний BGP процесс следующим образом:
   1. Номер AS — 107
   2. Создать ebgp сессию c маршрутизатором R4 следующим образом:
      1. Указать в качестве Remote AS номер 51
      2. Позволить увеличение значения TTL только до 2 хопов
      3. Указать в качестве Update Source интерфейс Loopback0
      4. Адвертайзить маршрут маршрут по-умолчанию
10. На маршрутизаторе R6 в процессе OSPF 107 редистрибьютить BGP процесс 107
11. На маршрутизаторе R4 настроить внешний BGP процесс следующим образом:
    1. Номер AS — 51
    2. Создать ebgp сессию c маршрутизатором R6 следующим образом:
       1. Указать в качестве Remote AS номер 107
       2. Позволить увеличение значения TTL только до 2 хопов
       3. Указать в качестве Update Source интерфейс Loopback0
       4. Редистрибьютить OSPF процесс 100 с метрикой 5
12. На маршрутизаторах R1, R2, R3, R4, R5 настроить внутренний BGP процесс следующим образом:
    1. Номер AS — 51
    2. Создать ibgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название INTERNAL
          2. Указать в качестве Remote AS номер 51
          3. Указать в качестве Update Source интерфейс Loopback0
13. На маршрутизаторах R6, R7, R8, R9, R10 настроить внутренний BGP процесс следующим образом:
    1. Номер AS — 107
    2. Создать ibgp сессию следующим образом:
       1. Создать BGP Peer Group:
          1. Название INTERNAL
          2. Указать в качестве Remote AS номер 107
          3. Указать в качестве Update Source интерфейс Loopback0
14. На интерфейсе E0/1.12 маршрутизаторов R1 и R2 отключить DoNotAge флаг в обновлениях OSPF.
15. Настроить интерфейсы E0/1.23 и E0/1.235 на маршрутизаторах R2, R3, R5 таким образом, чтобы транзитные маршруты от R2 до R4 не отображались в таблице маршрутизации R4.
16. На маршрутизаторах R1, R2, R6, R7, R8,R9, R10 настроить Incremental SPF
17. Настроить маршрутизатор R6 следующим образом:
    1. В LSDB должны сохраняться не более 5000 LSA
    2. Не более 5 маршрутов могут передаваться через редистрибьюцию
18. Настроить NSF на маршрутизаторах R4 и R5 следующим образом:
    1. R4 — включить NSF для Cisco:
       1. отключить Helper для Cisco
       2. включить IETF Helper
    2. R5 — включить NSF для IETF:
       1. включить Helper для Cisco
       2. отключить IETF Helper
