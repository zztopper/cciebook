---
description: 'Цикл 18, Тема 104:NetFlow'
---

# Лабораторная по теме 104

1. Загрузить начальную конфигурацию всех устройств \(использовать финальную конфигурацию из 103-й лабораторной работы\).
2. Для задания используется логическая и физическая топологии проекта.
3. Для задания используется конечная конфигурация лабораторной работы 103
4. На маршрутизаторе R6 настроить NetFlow следующим образом:
   1. Настроить учитывание входящего трафика на порту E0/1.456
   2. Настроить локальный коллектор трафика:
      1. Максимальное количество записей 10
      2. Сортировать по пакетам
   3. Настроить удаленный коллектор трафика:
      1. Указать IP адрес интерфейса Loopback0 маршрутизатора R1 порт 991
   4. Настроить версию 9
   5. Указать обновление кэш NetFlow данными о трафике еще активной сессии через каждые 3 минуты
   6. Настроить закрытие потока, если в течении 30 секунд не передаются данные.
   7. Указать в качестве источника отчета о трафике интерфейс E0/1.67
   8. Настроить Random Sampled Netflow cледующим образом:
      1. Наименование NETFLOW
      2. Настроить выборку в 1 пакет из 10
      3. Настроить ACL под названием R10\_R1:
         1. Разрешить трафик от IP адреса интерфейса Loopback0 маршрутизатора R10 к IP адресу интерфейса Loopback0 маршрутизатора R1
      4. Настроить Сlass Map под названием R10\_R1 и заматчить ACL R10\_R1
      5. Настроить Policy Map под названием NETFLOW:
         1. Применить Сlass Map под названием R10\_R1
         2. Применить Random Sampled Netflow под названием NETFLOW
      6. Применить Policy Map под названием NETFLOW на интерфейсе E0/1.67
      7. Настроить Netflow Aggregation Cache следующим образом:
         1. В качестве группировки указать Destination Prefix
         2. Разрешить кэш агрегации в 1024 записи
         3. Настроить таймаут активности в течении 15 минут
         4. Настроить таймаут неактивности в течении 1 минуту
         5. Применить на на входе в интерфейс E0/1.67
         6. Экспортировать кэш на удаленный коллектор, указанный в пункте 4.3

{% file src="../../.gitbook/assets/lab104\_answers.zip" caption="Конечная конфигурация" %}

