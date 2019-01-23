# Подготовка к лабораторной

Вам нужно будет импортировать файл топологии в свою Eve-NG или загрузить начальную конфигурацию.

{% file src="../.gitbook/assets/toplology\_logical\_ccie\_big\_lab\_2.pdf" caption="Логическая топология лабораторной" %}

{% file src="../.gitbook/assets/big\_lab2.unl.zip" caption="Топология для Eve-NG" %}

{% file src="../.gitbook/assets/biglab002.zip" caption="Начальная конфигурация" %}

Изменения топологии:

* Диагональные линки e3/2, e3/3 между коммутаторами выключены.
* Интерфейсы e3/1, e2/3 между коммутаторами выключены.
* Вместо DMVPN между r7 и r2, r3, r4 настроены GRE-туннели.
* На r6 выключен интерфейс e0/1.144
* На r3 и r2 выключен интерфейс e0/1.23
* На r5 выключен интерфейс e0/1.456

Советы:

* При выполнении заданий если вы заметили необычный конфиг, запишите его себе — вполне возможно, что это поможет вам решить последующие задания.
* Не забывайте включать обратно интерфейсы, если вы их выключали для теста.
* Проверки, указанные после задания, не гарантируют, что вы выполнили задание на 100% правильно.
* Будьте внимательны! Из-за неправильно выполненного подзадания вы можете получить 0 баллов за всё задание.
