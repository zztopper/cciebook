---
description: 'Цикл 3. Тема 15: Routing Protocol features'
---

# Лабораторная по теме 15

{% file src="../../.gitbook/assets/lab015.zip" caption="Начальная конфигурация" %}

Задание \#1 для лабораторной:  
1. Загрузить начальную конфигурацию на SW1, SW2, SW3, SW4, R1, R2, R3, R4, R5, R6, R7, R8, R9, R10  
_\* DMVPN туннели и подинтерфейсы Underlay сети, не участвуют в лабораторной работе._  
2. На всех маршрутизаторах настроить протокол динамической маршрутизации RIPv2 с анонсированием сетей 188.1.0.0 и 180.1.0.0  
3. Отключить автоматическое суммирование маршрутов на всех маршрутизаторах.  
4. Настроить на сегменте сети между маршрутизаторами R6-R4-R5 RIPv2 аутентификацию. Используйте режим MD5 и ключ 1 с паролем CCIEinaYEAR  
5. Сконфигурировать на сегменте сети между R9 и R10 для VLAN 109 параметры отправки и приема апдейтов только для протокола RIP версии 2.  
6. На сегменте сети между маршрутизаторами R4 и R3 настроить RIPv2 аутентификацию.Используйте режим clear text и ключ 1 с паролем CCIEtoBE  
7. Для сегмента сети между R6 и R7 VLAN 67, не использовать мультикаст и броадкаст для RIP сообщений.  
8. Отключить автоматическую отправку RIP сообщений на всех маршрутизаторах для интерфейсов не подключенных к другим устройствам или являющихся тупиковыми сетями \(подинтерфейсы и лупбек интерфейсы\).  
**Не использовать** правило default.  
9. Проверить с R1 доступность всех лупбек адресов всех маршрутизаторов с использованием протокола icmp.  
10. Если есть проблема с соединением решить ее

{% file src="../../.gitbook/assets/lab015\_answers.zip" caption="Конечная конфигурация" %}

