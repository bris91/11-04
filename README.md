## Задание 1. Установка RabbitMQ
Используя Vagrant или VirtualBox, создайте виртуальную машину и установите RabbitMQ. Добавьте management plug-in и зайдите в веб-интерфейс.

Итогом выполнения домашнего задания будет приложенный скриншот веб-интерфейса RabbitMQ.

![alt text](https://github.com/bris91/11-04/blob/b37167e0f8a33676d127968dd70a0fbcec2c1ea9/T_1.png)

## Задание 2. Отправка и получение сообщений
Используя приложенные скрипты, проведите тестовую отправку и получение сообщения. Для отправки сообщений необходимо запустить скрипт producer.py.

Для работы скриптов вам необходимо установить Python версии 3 и библиотеку Pika. Также в скриптах нужно указать IP-адрес машины, на которой запущен RabbitMQ, заменив localhost на нужный IP.

$ pip install pika
Зайдите в веб-интерфейс, найдите очередь под названием hello и сделайте скриншот. После чего запустите второй скрипт consumer.py и сделайте скриншот результата выполнения скрипта

В качестве решения домашнего задания приложите оба скриншота, сделанных на этапе выполнения.

![alt text](https://github.com/bris91/11-04/blob/b37167e0f8a33676d127968dd70a0fbcec2c1ea9/T_2.png)

![alt text](https://github.com/bris91/11-04/blob/b37167e0f8a33676d127968dd70a0fbcec2c1ea9/T_2.1.png)

## Задание 3. Подготовка HA кластера
Используя Vagrant или VirtualBox, создайте вторую виртуальную машину и установите RabbitMQ. Добавьте в файл hosts название и IP-адрес каждой машины, чтобы машины могли видеть друг друга по имени.

Пример содержимого hosts файла:

$ cat /etc/hosts
192.168.0.10 rmq01
192.168.0.11 rmq02
После этого ваши машины могут пинговаться по имени.

Затем объедините две машины в кластер и создайте политику ha-all на все очереди.

В качестве решения домашнего задания приложите скриншоты из веб-интерфейса с информацией о доступных нодах в кластере и включённой политикой.

![alt text](https://github.com/bris91/11-04/blob/b37167e0f8a33676d127968dd70a0fbcec2c1ea9/T_3.png)

![alt text](https://github.com/bris91/11-04/blob/b37167e0f8a33676d127968dd70a0fbcec2c1ea9/T_3.1.png)
Также приложите вывод команды с двух нод:

$ rabbitmqctl cluster_status

![alt text](https://github.com/bris91/11-04/blob/b37167e0f8a33676d127968dd70a0fbcec2c1ea9/T_3.2.png)

![alt text](https://github.com/bris91/11-04/blob/b37167e0f8a33676d127968dd70a0fbcec2c1ea9/T_3.3.png)


Для закрепления материала снова запустите скрипт producer.py и приложите скриншот выполнения команды на каждой из нод:

$ rabbitmqadmin get queue='hello'

![alt text]https://github.com/bris91/11-04/blob/b37167e0f8a33676d127968dd70a0fbcec2c1ea9/T_3.4.png
