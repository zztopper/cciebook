---
description: 'Цикл 5. Тема 30: Management Plane Security 7.2'
---

# Лабораторная по теме 30

{% file src="../../.gitbook/assets/lab030 \(1\).zip" caption="Начальная конфигурация" %}

Задание \#1 для лабораторной:  
1. Загрузить начальную конфигурацию R1, R2.  
2. На R2 создать локального пользователя под именем CCIEConsole c привилегией 15 и с шифрованным паролем CCIEinaConsole. Включить ААА.  
3. На R2 задать шифрованный пароль CCIEinaYEAR для Enable.  
4. На R2 создать authentication list под названием CONSOLE с использованием локальной базы пользователей и паролем. Применить его на консоли.  
5. На R2 создать authentication list под названием TELNET c использованием локальной базы пользователей, но паролем для Enable. Применить на терминальной линии.  
6. Настроить 3 максимальные попытки подключения.  
7. Настроить баннер, который будет требовать ввести пароль “Password Required” при подключении.  
8. Настроить баннер, который будет требовать ввести имя пользователя “Username Required” при подключении.  
9. Настроить баннер, который будет выводить сообщение “Authentication Failed , try again, при неудачной попытке аутентификации.  
10. На R2 настроить авторизацию exec по умолчанию с использованием локальной базы.

{% file src="../../.gitbook/assets/lab030\_answers.zip" caption="Конечная конфигурация" %}

