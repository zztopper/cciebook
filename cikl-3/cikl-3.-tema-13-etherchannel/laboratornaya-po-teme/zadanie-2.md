# Задание №2

{% file src="../../../.gitbook/assets/lab013\_task2.zip" caption="Начальная конфигурация" %}

1. Загрузить начальную конфигурацию на SW1, SW2, SW3, SW4  
2. На SW1 создать vlan 200 c ip 10.10.20.10/24, vlan 300 c ip 10.10.30.10/24, vlan 400 c ip 10.10.40.10/24  
3. На SW2 создать vlan 200 c ip 10.10.20.20/24.  
4. На SW3 создать vlan 300 c ip 10.10.30.30/24,  
5. На SW4 создать vlan 400 c ip 10.10.40.40/24  
6. Настроить агрегированный транковый интерфейс от коммутатора SW1 до коммутаторов SW2, SW3, SW4 с общим bandwidth до 20 Mb/s.  
При этом:  
· Между коммутаторами SW1 и SW2 не использовать протоколы автосогласования;  
· Между коммутаторами SW1 и SW3 использовать протокол автосогласования проприетарный протокол Cisco;  
· Между коммутаторами SW1 и SW4 использовать протокол автосогласования IEEE 802.3ad;  
· Только SW1 выступает в качестве активного инициатора процесса автосогласования;  
· Не использовать в качестве транкового протокола проприетарный протокол Cisco и режим автосогласования транка;  
· Разрешить на агрегированных транковых интерфейсах от SW1 до SW2,SW3,SW4 только те VLAN, для которых были созданы SVI интерфейсы на каждом из коммутаторов;  
· В качестве номера агрегированного канала использовать номера: 21, 31, 41 по аналогии с предыдущим заданием.  
7. Проверить настройки EtherChannel на всех коммутаторах.  
8. Отправить пинг на 255.255.255.255 с SW1 для проверки доступности всех SVI на коммутаторах.  
9. Настроить коммутаторы таким образом, чтобы приходящий на коммутатор IP пакет, с одним и тем же Source IP, но различными Destination IP распределялся по портам входящим в Etherchannel группу, однако при этом IP пакеты, с различными Source IP и одинаковым Destination IP отправлялись по одному и тому же интерфейсу.  
10. Переведите все неиспользуемые порты на всех четырех коммутаторах в состояние shutdown и настройте в режиме работы access в vlan 998  
  


{% file src="../../../.gitbook/assets/lab013\_task2\_answers.zip" caption="Конечная конфигурация" %}
