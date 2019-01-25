# Задание №6 по большой лабе 2

На r9 настроить отправку логов:

* Используя как транспорт TCP
* Логи должны отправляться на порт 10001
* Отправлять логи на Loopback0 r7
* Остальные параметры надо определить по выводу ниже
* Настроить r7 таким образом, чтобы TCP сессия между r9 и r7 установилась \(подсказка в выводе ниже\).

Вывод должен быть таким \(порты со стороны клиента могут быть любыми\):  
`R9#sh control-plane host open-ports  
Active internet connections (servers and established)  
Prot         Local Address             Foreign Address       Service State  
...  
 tcp               *:50254 180.1.7.7:10001                   Syslog ESTABLIS`  
`R7#sh control-plane host open-ports  
Active internet connections (servers and established)  
Prot           Local Address           Foreign Address       Service State  
...  
 tcp                 *:10001           *:0 HTTP CORE LISTEN  
 tcp                 *:10001 180.1.9.9:50254                HTTP CORE ESTABLIS`  


