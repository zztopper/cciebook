# Задание №1

{% file src="../../../.gitbook/assets/lab008\_task1.zip" caption="Начальная конфигурация" %}

1. Загрузить начальную конфигурацию для SW1, SW4, R6, R7  
2. Включить физический интерфейс E0/1 на маршрутизаторах R6 и R7.  
3. На маршрутизаторе R7 задать команду int virtual-template1 и командой sh int virtual-template1 проверить свойства созданного интерфейса и задать ip адрес 188.1.67.2/24  
4. Командой bba-group pppoe R6 определить BBA группу на сервере и привязать int virtual-template1 к группе.  
5. Зайти на интерфейс E0/1.67 маршрутизатора R7 и настроить команду pppoe enable group R6.  
6. На маршрутизаторе R6 командой int dial 1 создаем заданный интерфейс, настраиваем инкапсуляцию ppp, задаем ip 188.1.67.1/24, и задаем пул командой dialer pool 6  
7. Зайти на интерфейс E0/1.67 маршрутизатора R6 и привязать созданный пул к интерфейсу командой pppoe-client dial-pool-number 6  
8. С маршрутизатора R6 отправить пинг на ip 188.1.67.2  
  


{% file src="../../../.gitbook/assets/lab008\_task1\_answers.zip" caption="Конечная конфигурация" %}
