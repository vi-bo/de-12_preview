# Data Engineer 12.0 /  NewProLab / Spring 2023

### Источник

Сайт: [New Professions Lab](https://newprolab.com/#programmes)

### Практика

## Лаба 1. + 1s. [Настройка инфраструктуры + kafka-брокер](https://github.com/vi-bo/big_data/tree/main/de-12/lab1s)

### Задачи

* поднять две машины в VK Cloud с заданной конфигурацией;

* настроить порты в сети облака, подключиться к машинам по ssh;

* сконфигурировать группу правил доступа для внутрикластерного общения;

* установить Kafka, Zookeeper;

* настроить Firewall на уровне OS.

### Инструменты

![vk_cloud.png](./img/vk_cloud.png)
![apache_kafka.png](./img/apache_kafka.png)
![zookeeper.png](./img/zookeeper.png)
![kcat.png](./img/kcat.png)
![docker.png](./img/docker.png)

## Лаба 2. [Batch обработка данных e-commerce платформы](https://github.com/vi-bo/big_data/tree/main/de-12/lab2)

В лабе 2 и 3 делаем lambda-архитектуру с двумя слоями (batch-слоем и speed-слоем). В лабе 2 соответственно делаем batch-слой.

### Задачи

* установка и конфигурирование Сlickhouse;

* установка и конфигурирование Airflow;

* создание таблицы и материализованного представления в Clickhouse для получения и хранения в "сыром виде" данных из кафки, а также для хранения агрегированных по часам данных;

* проверка работы REST API Сlickhouse, Airflow;

* написать скрипт, который на основе сырых данных считает агрегаты и сохранит результат в нужную таблицу в Clickhouse;

* создание DAG Airflow, который запускает скрипт из предыдущего пункта;

* настройка пайплайна, чтобы чекер мог запускать DAG через REST API Airflow.

### Инструменты

![apache_kafka.png](./img/apache_kafka.png)
![clickhouse.png](./img/clickhouse.png)
![airflow.png](./img/airflow.png)

## Лаба 3. [Realtime обработка данных e-commerce портала](https://github.com/vi-bo/big_data/tree/main/de-12/lab3)

В лабе 2 и 3 делаем lambda-архитектуру с двумя слоями (batch-слоем и speed-слоем). В лабе 3 соответственно делаем speed-слой.

### Задачи

* установка Spark на VK Cloud / hadoop-кластере;

* проверка работоспособности Spark Streaming;

* проверка чтения/записи в топик Kafka;

* написать заготовку pyspark-джобы и скрипт для ее запуска;

* стриминг-расчёт метрик e-commerce платформы.

### Инструменты

![apache_kafka.png](./img/apache_kafka.png)
![spark.png](./img/spark.png)

## Лаба 3s. [Загрузка данных и построение витрин](https://github.com/vi-bo/big_data/tree/main/de-12/lab3s)

В лабе 2 и 3 делаем lambda-архитектуру с двумя слоями (batch-слоем и speed-слоем). В лабе 3 соответственно делаем speed-слой.

### Задачи

* создать базу данных и таблицы в Hive на hadoop-кластер;

* загрузить данные из Postgres спомощью Sqoop;

* построить датамарт в соответсивии с заданным условием.

### Инструменты

![hadoop.png](./img/hadoop.png)
![postgres.png](./img/postgres.png)
![sqoop.png](./img/sqoop.png)
![hive.png](./img/hive.png)
![spark.png](./img/spark.png)

## Лаба 4. [Web-сервис как data-product](https://github.com/vi-bo/big_data/tree/main/de-12/lab4)

В лабе 2 и 3 мы сделали lambda-архитектуру с двумя слоями (batch-слоем и speed-слоем). В лабе 4 делаем "сервис-слой".

### Задачи

* сделать топик Kafka для приема данных;

* загрузить данные из Kafka в ClickHouse с возможностью дозаписи новых данных;

* сделать микро-сервис на Flask;

* упаковать веб-сервис в Docker-контейнер.

### Инструменты

![apache_kafka.png](./img/apache_kafka.png)
![clickhouse.png](./img/clickhouse.png)
![flask.png](./img/flask.png)
![docker.png](./img/docker.png)

## Лаба 4s. [Дашборды, бизнесовые и опсовые](https://github.com/vi-bo/big_data/tree/main/de-12/lab4s)

Добавляем дашборды в сервис.

### Задачи

* взять данные из Clickhouse, сделать BI-аналитику с помощью Apache Superset;

* визуализация метрик Flask-приложения в Prometheus.

### Инструменты

![clickhouse.png](./img/clickhouse.png)
![superset.png](./img/superset.png)
![flask.png](./img/flask.png)
![docker.png](./img/docker.png)
![prometheus.png](./img/prometheus.png)

## Лаба 5. [Пайплайн персонализации для интернет-магазина](https://github.com/vi-bo/big_data/tree/main/de-12/lab5)

Сбор данных из нескольких источников, обогащение данных маппингом товар-категория из Postgres DB, расчет почасовых агрегатов по категориям и пользователям, сохранение результатов в Redis.

### Задачи

* развернуть новый Airflow и Redis в docker-контейнере;

* docker-compose для Airflow;

* загрузка данных кликстрима в Сlickhouse;

* exploratory data analysis (EDA) / предварительный анализ данных через DBeaver;

* распарсить дерево каталога товаров, обогатить данные кликстрима;

* DAG-обработчик для Airflow;

* расчет общих часовых характеристик по всем пользователям для категорий второго уровня (топ-5 добавленных в favorites);

* расчет персональных часовых данных пользователя для категорий третьего уровня (топ-10 просмотренных категорий, топ-5 добавленных в favorites);

* сохранить результаты в Redis.

### Инструменты

![postgres.png](./img/postgres.png)
![clickhouse.png](./img/clickhouse.png)
![airflow.png](./img/airflow.png)
![docker.png](./img/docker.png)
![redis.png](./img/redis.png)

## Шпаргалка

| Основные команды                                                                                                                                                                                                                  | Описание                                                                                                                                                                      |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ssh**                                                                                                                                                                                                                           |                                                                                                                                                                               |
| `ssh -i ./имя_файла_ключа.pem ubuntu@ip_адрес_удаленной_машины`                                                                                                                                                                   | подключение к удаленной машине по ключу (файл .pem должен лежать в папке .ssh)                                                                                                |
| `exit` , `logout` или `ctrl`+`d`                                                                                                                                                                                                  | выход из терминала удаленной машины                                                                                                                                           |
| `chmod 600 имя_файла_ключа.pem`                                                                                                                                                                                                   | изменение прав доступа для файла ключа, иначе данные будут считаться слишком открытыми                                                                                        |
| `host de-vi-bo-cn-1`                                                                                                                                                                                                              | после доступа в консоль удаленной машины - проверка доступа к удаленной машине по имени (ответ de-vi-bo-cn-1.mcs.local has address ip_адрес), первая машина была с внешним ip |
| `scp ./имя_файла_ключа.pem de12-cn-1:.ssh/id_rsa`                                                                                                                                                                                 | копирование файла ключа на удаленную машину в файл id_rsa (имя машины для доступа на de12-cn-1 поменял в файле config, папка .ssh)                                            |
| `scp /home/vibo/*.csv de12-cn-1:/home/ubuntu/`                                                                                                                                                                                    | копирование всех файлов типа csv на удаленную машину                                                                                                                          |
| `scp имя_файла de12-cn-1:/tmp`                                                                                                                                                                                                    | копирование файла из локалки на кластер                                                                                                                                       |
| `scp ubuntu@de12-cn-1:/путь_до_файла /home/vibo/Downloads/`                                                                                                                                                                       | копирование файла с удаленной машины на локальную                                                                                                                             |
| **firewall**                                                                                                                                                                                                                      |                                                                                                                                                                               |
| `sudo ufw status`                                                                                                                                                                                                                 | статус firewall (перед включением на удаленной машине - добавить порт 22 соединения по ssh)                                                                                   |
| `sudo ufw allow номер_порта/tcp`                                                                                                                                                                                                  | разрешить доступ к порту                                                                                                                                                      |
| `sudo ufw reload`                                                                                                                                                                                                                 | перезагрузка firewall                                                                                                                                                         |
| **ubuntu**                                                                                                                                                                                                                        |                                                                                                                                                                               |
| `sudo apt update && sudo apt -y full-upgrade`                                                                                                                                                                                     | обновление системных пакетов                                                                                                                                                  |
| `wget https://путь_до_архива/имя_архива.tgz`                                                                                                                                                                                      | скачать файл по прямой ссылке                                                                                                                                                 |
| `tar xzvf имя_архива.tgz`                                                                                                                                                                                                         | разархиварировать архив в текущий каталог                                                                                                                                     |
| `sudo mv имя_папки /opt/имя_папки`                                                                                                                                                                                                | перемещение папки с файлами                                                                                                                                                   |
| `java -version`                                                                                                                                                                                                                   | проверка установленной версии java                                                                                                                                            |
| `sudo cp ~/.bashrc ~/.bashrc_bak`                                                                                                                                                                                                 | бэкап переменных окружения (для spark)                                                                                                                                        |
| `source ~/.bashrc`                                                                                                                                                                                                                | применение изменений (после добавления записи о spark)                                                                                                                        |
| `echo "export AIRFLOW_HOME=/home/ubuntu/airflow/airflow_home" >> ~/.bash_profile`                                                                                                                                                 | установка значения переменной `AIRFLOW_HOME` в файл `~/.bash_profile`                                                                                                         |
| `spark`, `exit()`                                                                                                                                                                                                                 | запуск и выход из spark (если внести соответствующие изменения в файл )                                                                                                       |
| `chmod 755 имя_скрипта.sh`                                                                                                                                                                                                        | расширение прав на использование скрипта                                                                                                                                      |
| `./имя_скрипта.sh`                                                                                                                                                                                                                | запуск скрипта                                                                                                                                                                |
| `chmod +x ./имя_скрипта.sh`                                                                                                                                                                                                       | делаем скрипт выполняемым                                                                                                                                                     |
| **venv**                                                                                                                                                                                                                          |                                                                                                                                                                               |
| `sudo apt install python3.10-venv`                                                                                                                                                                                                | установка venv                                                                                                                                                                |
| `python3 -m venv имя`                                                                                                                                                                                                             | создание нового виртуального окружения                                                                                                                                        |
| `source имя/bin/activate`                                                                                                                                                                                                         | активация виртуального окружения                                                                                                                                              |
| `pip freeze > requirements.txt`                                                                                                                                                                                                   | сохранение файла с зависимостями                                                                                                                                              |
| **virtualenv**                                                                                                                                                                                                                    |                                                                                                                                                                               |
| `virtualenv -p /usr/bin/python3 имя`                                                                                                                                                                                              | создание виртуальной среды                                                                                                                                                    |
| `source /home/ubuntu/airflow/имя/bin/activate`                                                                                                                                                                                    | активация виртуальной среды                                                                                                                                                   |
| `export AIRFLOW_HOME="pwd"/airflow_home`                                                                                                                                                                                          | установка переменной среды `AIRFLOW_HOME`                                                                                                                                     |
| **systemctl**                                                                                                                                                                                                                     |                                                                                                                                                                               |
| `sudo systemctl status имя_сервиса`                                                                                                                                                                                               | проверка работоспособности сервиса                                                                                                                                            |
| `sudo systemctl start имя_сервиса`                                                                                                                                                                                                | запуск сервиса                                                                                                                                                                |
| `sudo systemctl stop имя_сервиса`                                                                                                                                                                                                 | остановка сервиса                                                                                                                                                             |
| `sudo systemctl enable имя_сервиса`                                                                                                                                                                                               | добавление сервиса в автозагрузку                                                                                                                                             |
| `sudo systemctl disable имя_сервиса`                                                                                                                                                                                              | удаление сервиса из автозагрузки                                                                                                                                              |
| `sudo systemctl restart имя_сервиса`                                                                                                                                                                                              | перезапуск сервиса                                                                                                                                                            |
| **kafka**                                                                                                                                                                                                                         |                                                                                                                                                                               |
| `docker run -it --network=host edenhill/kcat:1.7.1 -b адрес:9092 -L`                                                                                                                                                              | посмотреть топики и метаданные (с другой машины) через kcat                                                                                                                   |
| `docker run -it --network=host edenhill/kcat:1.7.1 -b адрес:9092 -C -t имя_топика`                                                                                                                                                | слушаем (консьюмим -С) топик кафки, запущенной через                                                                                                                          |
| `/opt/kafka_2.13-3.2.3/bin/kafka-topics.sh --create --topic имя_топика --bootstrap-server localhost:9092 --config retention.ms=300000`                                                                                            | создание топика кафки, с помощь консольной утилиты                                                                                                                            |
| `/opt/kafka_2.13-3.2.3/bin/kafka-topics.sh --create --topic имя_топика --bootstrap-server localhost:9092`                                                                                                                         | создание топика кафки, с помощь кафки, с помощью консольной утилиты                                                                                                           |
| `docker run -it --network=host edenhill/kcat:1.7.1 -b адрес:9092 -P -t имя_топика`                                                                                                                                                | продьюсить в топи -Р (с другой машины) через kcat                                                                                                                             |
| **hdfs / hive / sqoop**                                                                                                                                                                                                           |                                                                                                                                                                               |
| `hdfs dfs -ls /user`                                                                                                                                                                                                              | просмотр дирректории                                                                                                                                                          |
| `hdfs dfs -rm -rf -f /tmp/имя_папки`                                                                                                                                                                                              | очистака папки (удалится в корзину)                                                                                                                                           |
| `hive`                                                                                                                                                                                                                            | запуск hive                                                                                                                                                                   |
| `create database vi_bo location '/user/vi.bo/warehouse';`                                                                                                                                                                         | инициализация базы данных                                                                                                                                                     |
| `use vi_bo;`                                                                                                                                                                                                                      | вход в базу данных                                                                                                                                                            |
| `show tables;`                                                                                                                                                                                                                    | просмотр перечня таблиц                                                                                                                                                       |
| `drop table имя_таблицы;`                                                                                                                                                                                                         | удаление таблицы                                                                                                                                                              |
| `show create имя_таблицы;`                                                                                                                                                                                                        | просмотр параметров таблицы                                                                                                                                                   |
| `sqoop import --help;`                                                                                                                                                                                                            | вызов справки по sqoop                                                                                                                                                        |
| `sqoop import --connect jdbc:postgresql://адрес:5432/имя_базы_данных --driver org.postgresql.Driver --password **** --username **** --table имя_таблицы -m 1 --target-dir /user/vi.bo/warehouse/stg_имя_таблицы --as-parquetfile` | загрузка данных из postgres в hdfs через sqoop                                                                                                                                |
| **clickhouse**                                                                                                                                                                                                                    |                                                                                                                                                                               |
| `sudo chmod 755 /etc/clickhouse-server/config.xml`                                                                                                                                                                                | расширение прав, чтобы не было проблем при запуске                                                                                                                            |
| `clickhouse+native://адрес:9090/default`                                                                                                                                                                                          | подключение к открытой базе данных (default)                                                                                                                                  |
| `sudo clickhouse-client --9090 `                                                                                                                                                                                                  | запуск клиента                                                                                                                                                                |
| `show tables`                                                                                                                                                                                                                     | перечень созданных таблиц                                                                                                                                                     |
| `clickhouse-client --port 9090 --query="show databases"`                                                                                                                                                                          | просмотр перечня баз данных                                                                                                                                                   |
| `clickhouse-client --port 9090 --query="show tables"`                                                                                                                                                                             | просмотр перечня таблиц                                                                                                                                                       |
| `clickhouse-client --port 9090 --query="show create table имя_таблицы"`                                                                                                                                                           | просмотр таблицы                                                                                                                                                              |
| `clickhouse-client --port 9090 --query="select * from имя_таблицы limit 10"`                                                                                                                                                      | просмотр данных таблицы                                                                                                                                                       |
| `clickhouse-client --port 9090 --query="select count(*) from имя_таблицы"`                                                                                                                                                        | проверка количества записей таблицы                                                                                                                                           |
| `sudo mv /home/ubuntu/имя_файла.jsonl /var/lib/clickhouse/user_files/имя_файла.jsonl`                                                                                                                                             | перенос файла в рабочий каталог (иначе было не создать таблицу из этого файла)                                                                                                |
| `sudo clickhouse-client --port 9090 --multiline --query="CREATE TABLE имя_таблицы ENGINE=File(JSONEachRow, 'имя_файла.jsonl')"`                                                                                                   | создание таблицы из файла формата jsonl                                                                                                                                       |
| `cat /tmp/имя_файла.json \| clickhouse-client --port 9090 --multiline --query="INSERT into имя_таблицы JSONEachRow"`                                                                                                              | загрузка данных из json файла в таблицу                                                                                                                                       |
| `select count(*) from имя_таблицы;`                                                                                                                                                                                               | проверка количества записей в таблице                                                                                                                                         |
| `select * from имя_таблицы limit 10;`                                                                                                                                                                                             | прсомотр 10 записей таблицы                                                                                                                                                   |
| `select имя_колонки_1, имя_колонки_2, timestamp, toDateTime(timestamp) as time_stamp from имя_таблицы limit 10;`                                                                                                                  | преобразование столбца `timestamp` к времени и дате, с выводом 10 записей                                                                                                     |
| `drop table имя_таблицы`                                                                                                                                                                                                          | удаление таблицы                                                                                                                                                              |
| `curl -X GET http://localhost:8123/`                                                                                                                                                                                              | проверка REST API                                                                                                                                                             |
| `curl -v -X GET http://localhost:8123/`                                                                                                                                                                                           | проверка REST API (с получением кодов ответа)                                                                                                                                 |
| `curl -X GET http://адрес:8123/`                                                                                                                                                                                                  | проверка REST API извне                                                                                                                                                       |
| **airflow**                                                                                                                                                                                                                       |                                                                                                                                                                               |
| `airflow version`                                                                                                                                                                                                                 | версия                                                                                                                                                                        |
| `airflow db init`                                                                                                                                                                                                                 | инициализация базы данных                                                                                                                                                     |
| `airflow webserver -p 8081`                                                                                                                                                                                                       | запуск приложения на порту 8081 из виртуальной среды                                                                                                                          |
| `airflow config get-value webserver web_server_port`                                                                                                                                                                              | проверяем на каком порту запущен airflow (из виртуальной среды)                                                                                                               |
| `airflow users create -r Admin -u admin -f Vi -l Bo -e vi.bo7@ya.ru -p '***pass***'`                                                                                                                                              | создание пользователя бд airflow (в контейнере airflow)                                                                                                                       |
| **docker**                                                                                                                                                                                                                        |                                                                                                                                                                               |
| `sudo docker images`                                                                                                                                                                                                              | просмотр загруженных образов                                                                                                                                                  |
| `docker ps`                                                                                                                                                                                                                       | список запущенных контейнеров                                                                                                                                                 |
| `docker ps -a`                                                                                                                                                                                                                    | история запуска контейнеров                                                                                                                                                   |
| `sudo docker exec -it номер_контейнера bash`                                                                                                                                                                                      | войти в bash контейнера (вместо bash может )                                                                                                                                  |
| `sudo docker image rm номер_образа`                                                                                                                                                                                               | удаление образа контейнера                                                                                                                                                    |
| `sudo docker build --tag имя_образа .`                                                                                                                                                                                            | сборка/пересборка образа в текущей дирректории                                                                                                                                |
| `sudo docker run --rm -p 7000:5000 имя_контейнера:latest`                                                                                                                                                                         | запуск контейнера с флагом --rm (удаление после завершения) на порту 7000 (внутри приложение работает на порту 5000)                                                          |
| `sudo docker run --rm -p 7000:5000 flask_приложение:latest`                                                                                                                                                                       | запуск flask-приложения на порту 7000 (внутри работает на 5000)                                                                                                               |
| `sudo docker run -d --rm -p 7000:5000 flask_приложение:1.0.0`                                                                                                                                                                     | запуск контейнера с flask-приложением на порту 7000 (внутри приложение работает на порту 5000), флаг -d - работа в фоновом режиме                                             |
| **docker-compose**                                                                                                                                                                                                                |                                                                                                                                                                               |
| `sudo apt-get install docker-compose-plugin`                                                                                                                                                                                      | установка                                                                                                                                                                     |
| `docker compose version`                                                                                                                                                                                                          | проверка версии                                                                                                                                                               |
| `sudo docker compose up`                                                                                                                                                                                                          | запуск файла docker-compose.yml                                                                                                                                               |
| `docker-compose exec имя_контейнера bash`                                                                                                                                                                                         | войти в bash контейнера (не работало)                                                                                                                                         |
| `sudo docker-compose -f имя_файла.yml up`                                                                                                                                                                                         | запуск контейнера с приложением                                                                                                                                               |
| `sudo docker-compose -f имя_файла.yml down`                                                                                                                                                                                       | остановка контейнера с приложением                                                                                                                                            |
| **flask**                                                                                                                                                                                                                         |                                                                                                                                                                               |
| `pip install Flask==2.1.2`                                                                                                                                                                                                        | ставим flask заданной версии                                                                                                                                                  |
| `curl -XGET localhost:5000/health`                                                                                                                                                                                                | тестовая ручка health, локальная проверка                                                                                                                                     |
| `curl -XGET http://адрес:7000/health`                                                                                                                                                                                             | проверка работоспособности приложения по сделанной ручке health (5000 порт без докера)                                                                                        |
| `curl -XGET 'http://localhost:7000/params?param1="hello"&param2=20'`                                                                                                                                                              | проверка работоспособности приложения, запущенного локально, ручка params                                                                                                     |
| **redis**                                                                                                                                                                                                                         |                                                                                                                                                                               |
| `redis-cli`                                                                                                                                                                                                                       | вход в клиент                                                                                                                                                                 |
| `ping`                                                                                                                                                                                                                            | проверка работы (ответ - `PONG`)                                                                                                                                              |
| `zrange имя_ключа 0 -1 withscores`                                                                                                                                                                                                | проверка записей по ключу                                                                                                                                                     |
| `flushall`                                                                                                                                                                                                                        | полная очистка базы данных                                                                                                                                                    |
| `exit`                                                                                                                                                                                                                            | выход                                                                                                                                                                         |
| **superset**                                                                                                                                                                                                                      |                                                                                                                                                                               |
| `http://адрес:8088/superset/welcome/`                                                                                                                                                                                             | стартовая страница, регистрация по умолчанию admin/admin                                                                                                                      |
| **prometheus**                                                                                                                                                                                                                    |                                                                                                                                                                               |
| `pip install prometheus-flask-exporter`                                                                                                                                                                                           | плагин для сбора данных из приложения, устанавливается в виртуальное окружение                                                                                                |
| `sudo prometheus --web.listen-address=:9000 &`                                                                                                                                                                                    | запуск локально установленного prometheus на порту 9000                                                                                                                       |
| `sudo docker run -p 9000:9090 -v /etc/prometheus/prometheus.yml: /etc/prometheus/prometheus.yml prom/prometheus`                                                                                                                  | запуск из контейнера с заданной конфигурацией (prometheus.yml) на порту 9000 (внутри контейнера работает на 9090, поменял, чтобы не конфликтовал с ClickHouse)                |
| `DEBUG_METRICS=1 python flask_приложение.py`                                                                                                                                                                                      | запуск flask-приложения с переменной окружения, разрешающей сбор метрик                                                                                                       |
| `flask_http_request_duration_seconds_count{path="/health"}`                                                                                                                                                                       | через UI pronetheus дергаем ручку приложения для проверки отрисовки графика                                                                                                   |
