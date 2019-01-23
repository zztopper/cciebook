---
description: 6 баллов
---

# Задание №3

Настройте r1 и r7 согласно выводу команд ниже.  
Параметры SSH:

* Доменное имя: linkmeup.ru
* Размер RSA ключа должен быть 1024 бит
* Из протоколов удаленного доступа только SSH должен быть разрешён
* Использовать локальную базу пользователей для аутентификации \(на r1 пользователь cisco/cisco преднастроен\)
* Версия SSH: 2

Ограничения:

* Нельзя использовать NAT для решения задачи.
* Нельзя менять IP-адреса
* Номер vty имеет значение
* Совет: не используйте аутентификацию по ключам, в этом задании

Остальные настройки нужно определить из вывода ниже \(порт со стороны клиента может быть любым\):  
`R2#ssh -l cisco -p 3009 180.1.1.1  
Password:  
R7> sh users  
    Line       User Host(s)              Idle Location  
   0 con 0                idle 00:01:27  
*  5 vty 3     ccie idle                 00:00:00 188.1.12.1`

`R7> sh control-plane host open-ports  
Active internet connections (servers and established)  
Prot      Local Address        Foreign Address        Service State  
...  
 tcp             *:9009         *:0 SSH-Server LISTEN  
 tcp             *:9009 188.1.12.1:45963           SSH-Server ESTABLIS`  


Вывод с r1:  
`R1#sh users  
    Line       User Host(s)              Idle Location  
*  0 con 0                idle 00:00:00  
   5 vty 3     cisco 180.1.7.7            00:00:06 188.1.12.2`

