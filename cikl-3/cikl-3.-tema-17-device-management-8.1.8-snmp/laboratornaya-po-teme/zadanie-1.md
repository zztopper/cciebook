# Задание №1

{% file src="../../../.gitbook/assets/lab017\_task1.zip" caption="Начальная конфигурация" %}

1. Загрузить начальную конфигурацию
2. На R1,R2,R3,R4,R5,R6 создать view SNMP сервера версии 3 под названием ALLINT и разрешить доступ для всех объектов интерфейса \(к соответствующему поддереву MIB\).
3. На R1,R2,R3,R4,R5,R6 создать группу под названием CCIEinaYEAR с использованием SNMP версии 3 и дать разрешение на чтение и запись для view ALLINT.
4. На R1,R2,R3,R4,R5,R6 создать пользователя под названием CCIEadmin, привязать его к группе CCIEinaYEAR c доступом на чтение и запись по протоколу SNMP, только в случае если пользователь пройдет SNMP аутентификацию:
   * Использовать аутентифкацию sha с паролем CCIEinaYEAR? , параметрами шифрования 3des и паролем шифрования CCIEinaYEAR?
   * Разрешить доступ для пользователя CCIEadmin только с адреса 180.1.3.3 используя ACL с номером 90
5. В конце конфигурации каждого устройства, добавить вывод команды sh snmp user

{% file src="../../../.gitbook/assets/lab017\_task1\_answers.zip" caption="Конечная конфигурация" %}
