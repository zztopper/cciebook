---
description: 'Цикл 7. Тема 38: Object Tracking 9.1, IP SLA'
---

# Лабораторная по теме

{% file src="../../.gitbook/assets/lab038.zip" caption="Начальная конфигурация" %}

Задание \#1 для лабораторной:  
1. Загрузить начальную конфигурацию всех устройств.  
2. В задании используется логическая топология проекта без DMVPN.  
3. На всех мартшрутизаторах настроить протокол маршрутизации Named EIGRP с названием IPSLA с номером автономной системы 10. При этом должны анонсироваться сети 188.1.0.0 и 180.1.0.0  
4. На R10 настроить http server следующим образом:  
  а\) К нему должен получать доступ только R1 c ip адресом 188.1.12.1 на порту 80.  
  в\) Сервер должен отвечать на этот запрос.  
5. На R1 создать IP SLA со следующей настройкой:  
IP SLA под номером 1 для отправки HTTP get запроса на R10.  
6. На R10 настроить симуляцию ответа на запрос голосового трафика следующим образом:  
Настроить IP SLA Responder для ответы на на все udp запросы R1 c ip адреса 188.1.12.1 .  
7. На R1 создать IP SLA со следующей настройкой:  
  а\) IP SLA под номером 2 для симуляции проверки производительности сети на голосовой трафик. Запрос отправляется на R10. Настроить проверку jitter для проверки по кодеку g729a.  
8. На R1 создать IP SLA со следующей настройкой:  
  а\) IP SLA под номером 3 для проверки задержек на каждом маршрутизаторе от R1 до R10.

В конце конфига R1 выложить вывод команды sh ip sla statistics

{% file src="../../.gitbook/assets/lab038\_answers.zip" caption="Конечная конфигурация" %}
