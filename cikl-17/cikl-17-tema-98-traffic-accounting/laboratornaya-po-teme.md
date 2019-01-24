---
description: 'Цикл 17, Тема 98: Traffic Accounting'
---

# Лабораторная по теме

1. Для задания используется конечные конфиги лабораторной работы 97.
2. На маршрутизаторе R6 настроить передачу только маршрута по-умолчанию следующим образом:
   1. настроить ACL под названием DEFAULT и разрешить только трафик маршрута по-умолчанию.
   2. в протоколе BGP настроить Distribute List c ACL под названием DEFAULT на выход.
3. На маршрутизаторах R2, R3, R7 настроить IP Precedence Accounting следующим образом:
   1. На маршрутизаторе R2:
      1. настроить ACL под названием ICMP разрешить весь трафик ICMP
      2. настроить Class Map под названием ICMP и заматчить ACL под названием ICMP
      3. настроить Policy Map под названием ICMP, классифицировать Class Map под названием ICMP и проставить Precedence 5
      4. применить Policy Map под названием ICMP на интерфейсе Ethernet 0/1.144
      5. настроить на интерфейсе Tunnel0 Qos Pre-classification
   2. На маршрутизаторе R3:
      1. На маршрутизаторе R3 настроить IP Precedence Accounting следующим образом:
      2. настроить ACL под названием TELNET разрешить весь трафик TELNET
      3. настроить Class Map под названием TELNET и заматчить ACL под названиемTELNET
      4. настроить Policy Map под названием TELNET, классифицировать Class Map под названием TELNET и проставить Precedence 3
      5. применить Policy Map под названием TELNET на интерфейсе Ethernet 0/1.144
      6. настроить на интерфейсе Tunnel0 Qos Pre-classification
   3. Настроить на интерфейсе Ethernet 0/1.144 маршрутизатора R7 в IP Precedence Accounting
4. На маршрутизаторе R7 настроить IP Access Violation Accounting следующим образом:
   1. настроить ACL под названием BLOCK\_R2L0\_TO\_R8L0 и запретить весь трафик от IP адреса интерфейса Loopback0 маршрутизатора R2 к IP адресу интерфейса Loopback0 маршрутизатора R8. Разрешить весь остальной трафик
   2. применить ACL под названием BLOCK\_R2L0\_TO\_R8L0 на выходе интерфейса Ethernet 0/1.78
   3. настроить на интерфейсе Ethernet 0/1.78 IP Access Violation Accounting
5. На маршрутизаторе R7 настроить IP Output Packet Accounting следующим образом:
   1. настроить IP Accounting List для IP адреса интерфейса Loopback0 маршрутизатора R10.
   2. настроить на интерфейсе Ethernet 0/1.78 IP Output Packet Accounting
6. Проверить работу всех настроек.

{% file src="../../.gitbook/assets/lab098\_answers.zip" caption="Конечная конфигурация" %}

