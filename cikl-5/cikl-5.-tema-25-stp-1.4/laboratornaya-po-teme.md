---
description: 'Цикл 5. Тема 25: STP 1.4'
---

# Лабораторная по теме

{% file src="../../.gitbook/assets/lab025.zip" caption="Начальная конфигурация" %}

Задание \#1 для лабораторной:  
1. Загрузить начальную конфигурацию R1, R2,R4, SW1, SW2, SW3, SW4.  
2. Назначить SW1 Root Bridge используя команду root primary для vlan 10.  
3. Выполнить следующие настройки на всех коммутаторах для vlan 10:  
  • Уменьшить время отправки Сonfiguration BPDU на половину от значения по умолчанию.  
  • Уменьшить максимальное время ожидания BPDU пакетов на половину от значения по умолчанию.  
  • Уменьшить время обновления MAC-таблиц в случае получения сообщения об изменении топологии на треть от значения по умолчанию.  
4. Порты E0/0 на SW1 и SW4 коммутаторах перевести в режим, в котором при изменении состояния порта не будет отправляться TCN.  
5. На SW4 настроить режим, который позволяет коммутаторам обновить записи в таблицах коммутации без использования TCN при падении Root Port на SW4.  
6. На всех коммутаторах настроить режим, который позволяет быстрее найти альтернативный путь, после изменения топологии, устанавливая MaxAge как “Истекший”.  
7. Порты E0/0 на SW1 и SW4 коммутаторах настроить таким образом, чтобы BPDU сообщение не отправлялись и не принимались.  
8. Настроить SW1 таким образом, чтобы на порту e0/1 BPDU не принимались и не отправлялись, но в случае получения BPDU на данном порте данный порт мог учитываться в STP-домене.  
9. Порты E0/0 на SW1 и SW4 коммутаторах настроить таким образом, чтобы при получении BPDU они переходили в режим Error disable.  
10. На SW1 и SW4 настроить время восстановления портов, попавших под режим Error disable вследствие получения BPDU за 30 секунд.  
11. Порты E0/0 на SW1 и SW4 коммутаторах настроить таким образом, чтобы при получении Superior BPDU они переставали передавать трафик.

{% file src="../../.gitbook/assets/lab025\_answers.zip" caption="Конечная конфигурация" %}
