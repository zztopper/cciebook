---
description: 'Цикл 10, Тема 59: Miscellaneous System Management'
---

# Лабораторная по теме

{% file src="../../.gitbook/assets/lab059.zip" caption="Начальная конфигурация" %}

Задание

1. Загрузить начальную конфигурацию устройств.
2. Для задания используется физическая топологии проекта.
3. На маршрутизаторах R1 и R5 настроить buffer tuning следующим образом:
   1. Public Buffer Pool:
      1. Small buffers initial = 250, min-free, max-free и permanent до соответствующих показателей в Middle buffers
4. Решить проблему cdp на SW1 и SW5
5. Настроить на R5 доступ по Remote Shell следующим образом:
   1. Настроить ACL, где разрешить доступ ip 10.0.0.1
   2. Привязать ACL к RSH
   3. Создать пару пользователь/пароль R1/RSH с привелегией 15
6. Попробовать подключиться через RSH

{% file src="../../.gitbook/assets/lab059\_answers.zip" caption="Конечная конфигурация" %}

