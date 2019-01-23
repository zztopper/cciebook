---
description: 'Цикл 7. Тема 37: STP 1.4'
---

# Лабораторная по теме

{% file src="../../.gitbook/assets/lab037.zip" caption="Начальная конфигурация" %}

1\) Загрузить начальную конфигурацию R2,R3,R4, R5, SW1, SW2, SW3, SW4.  
2\) Для задания используется логическая и физическая топологии проекта.  
3\) Все настройки делаются в одном регионе. Название региона: REGION1.  
4\) Настроить MST на коммутаторах следующим образом:

* Трафик вланов, относящихся к R2 и R3:
  * Должен идти сначала SW1-SW2-SW3, если падает SW2, то SW1-SW4-SW3, если падает SW4, то SW1-SW3.
  * В конфигурации не менять настройки портов.
  * Отнести все вланы в MST 23.
  * Назначить SW2 root в MST 23, используя команду с указанием приоритета.
* Трафик вланов, относящихся к R3 и R4:
  * Должен идти сначала SW3-SW1-SW4, если падает SW1, SW3-SW2-SW4, если падает SW2, то SW3-SW4.
  * В конфигурации не менять настройки портов.
  * Отнести все вланы в MST 34.
  * Назначить SW1 root в MST 34, используя команду macro.
* Трафик вланов, относящихся к R3 и R5:
  * Должен идти сначала SW3-SW4-SW2, если падает SW4, SW3-SW1-SW2, если падает SW1, то SW3-SW2.
  * В конфигурации не менять настройки портов.
  * Отнести все вланы в MST 235.
  * Назначить SW4 root в MST 235, используя команду с указанием приоритета.

5\) Назначить SW1 CIST Root для REGION1.

{% file src="../../.gitbook/assets/lab037\_answers.zip" caption="Конечная конфигурация" %}
