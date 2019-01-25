# Задание №8 по 1 большой лабе

На R3 настройте плавающий статический дефолтный маршрут:  
— Основной маршрут должен идти через R4 \(188.1.34.4\).  
— Запасной маршрут должен идти через R5 \(188.1.235.5\) и вступать в силу только, если line protocol интерфейса e0/1.34 на R3 в down.  
_\* Заметка: для этого задания нельзя использовать track_  
Для теста используйте R6 Loopback0 \(180.1.6.6\)

Проверка:

`R3#trace 180.1.6.6 so lo0 nu  
Type escape sequence to abort.  
Tracing the route to 180.1.6.6  
VRF info: (vrf in name/id, vrf out name/id)  
1 188.1.34.4 2 msec 1 msec 2 msec  
2 188.1.45.6 2 msec 2 msec 2 msec  
R3#conf t  
R3(config)#int e0/1.34  
R3(config-subif)#shut  
R3(config-subif)#end  
R3#trace 180.1.6.6 so lo0 nu  
Type escape sequence to abort.  
Tracing the route to 180.1.6.6  
VRF info: (vrf in name/id, vrf out name/id)  
1 188.1.235.5 2 msec 0 msec 0 msec  
2 188.1.45.6 2 msec 1 msec 1 msec`

