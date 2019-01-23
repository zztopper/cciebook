---
description: 4 балла
---

# Задание №2

R2 должен пинговать IP адрес R1 Loopback0 \(180.1.1.1\) и путь до него должен проходить через s1/0.  
Если интерфейс s1/0 в состоянии down, то пинг должен идти через e0/1.12  
**Нельзя** изменять существующие и добавлять новые статические маршруты, использование PBR также **запрещено**.  
  
**Проверка**:

`R2#ping 180.1.1.1  
Type escape sequence to abort.  
Sending 5, 100-byte ICMP Echos to 180.1.1.1, timeout is 2 seconds:  
!!!!!  
Success rate is 100 percent (5/5), round-trip min/avg/max = 5/7/9 ms  
R2#show ip cef | i 180.1.1.1  
180.1.1.1/32 attached Serial1/0  
R2#conf t  
R2(config)#int s1/0  
R2(config-if)#shut  
R2(config-if)#end  
R2#ping 180.1.1.1  
Type escape sequence to abort.  
Sending 5, 100-byte ICMP Echos to 180.1.1.1, timeout is 2 seconds:  
!!!!!  
Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/1 ms  
R2#show ip cef | i 180.1.1.1  
180.1.1.1/32 188.1.12.1 Ethernet0/1.12`

