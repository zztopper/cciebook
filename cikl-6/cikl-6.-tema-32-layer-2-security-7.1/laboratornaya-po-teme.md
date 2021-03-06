---
description: 'Цикл 6. Тема 32: Layer 2 Security 7.1'
---

# Лабораторная по теме 32

{% file src="../../.gitbook/assets/lab032.zip" caption="Начальная конфигурация" %}

Задание \#1 для лабораторной:  
1. Загрузить начальную конфигурацию R1, R5, SW1, SW2.  
2. Назначить SW1 Root Bridge используя команду root primary для vlan 10, определив максимальное количество коммутаторов между R1 и R5 равное 2, уменьшив при этом время отправки BPDU на половину от значения по умолчанию.  
3. Назначить SW2 Secondary Root Bridge используя команду root secondary для vlan 10, определив максимальное количество коммутаторов между R1 и R5 равное 2, уменьшив при этом время отправки BPDU на половину от значения по умолчанию.  
4. Порты E0/0 на SW1 и S2 коммутаторах перевести в режим, в котором при изменении состояния порта не будет отправляться TCN, а также в режим работы point-to-point.  
5. Перевести все транковые порты на коммутаторах в режим работы point-to-point.  
6. Назначить SW1 в роли аутентификатора, выполнив следующие настройки:  
• Включить aaa new model.  
• Создать список метода аутентификации, который будет применяться по умолчанию ко всем портам. Также указать список всех серверов аутентификации Radius.  
• Настроить коммутатор для авторизации на Radius серверах, для запросов всех сетевых сервисов.  
• Включить 802.1x аутентификацию на коммутаторе глобально  
• Указать в качестве Radius сервера R5 c ключом CCIEinaYEAR  
• Настроить порт E0/0 в режиме работы single-host, указать очередность аутентификации сначала 802.1 x, затем MAB. Включить МАВ и аутентификацию на порту. Настроить период таймаута в 5 секунд для повторного запроса от Supplicant. Настроить порт в качестве Authenticator.

{% file src="../../.gitbook/assets/lab032\_answers.zip" caption="Конечная конфигурация" %}

