# Задание №2

{% file src="../../../.gitbook/assets/lab007\_task2.zip" caption="Начальная конфигурация" %}

Подготовка лабораторной:

1. Загрузить начальную конфигурацию на SW1, SW2, SW3, SW4 .

Конфигурация

1. На SW4 создать следующие VLAN: 10, 20, 30, 40, 50, 60, 333. На коммутаторе SW4 настроить VTP, в режиме ограничения нежелательного трафика к коммутаторам, не использующих какие либо VLANы из списка для коммутации трафика.
2. Перевести SW1 в режим, при котором коммутатор может изменять VLAN Database только на основании обновлений VTP.
3. Проверить синхронизацию VLAN database на коммутаторе SW1.
4. На коммутаторе SW4 добавить интерфейс Ethernet 0/3 в VLAN 60, и включить его командой no shutdown.
5. На коммутаторе SW3 добавить интерфейс Ethernet 0/3 в VLAN 333, и включить его командой no shutdown.
6. Проверить работу VTP Pruning на всех коммутаторах командой sh int pruning, sh int trunk.
7. Настроить интерфейс eth0/0 на SW1 в режиме транк.
8. Проверить работу VTP Pruning командой sh int pruning, sh int trunk.
9. Разрешить на интерфейсе eth0/0 работу только следующих VLAN’ов: 10, 20, 30, 40 командой switchport trunk allowed vlan 10, 20, 30, 40.
10. Проверить работу VTP Pruning командой sh int pruning.
11. В VTP домене назначить пароль CCIEinaYEAR. Командой sh vtp status проверить идентичность номера ревизии и md5 hash на всех коммутаторах.

{% file src="../../../.gitbook/assets/lab007\_task2\_answers.zip" caption="Конечная конфигурация" %}
