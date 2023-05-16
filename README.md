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

* взять данные из Clickhouse, сделать BI-аналитику, с помощью Apache Superset;

* визуализация метрик Flask-приложения в Prometheus.

### Инструменты

![clickhouse.png](./img/clickhouse.png)
![superset.png](./img/superset.png)
![flask.png](./img/flask.png)
![docker.png](./img/docker.png)
![prometheus.png](./img/prometheus.png)

## Лаба 5. [Пайплайн персонализации для интернет-магазина](https://github.com/vi-bo/big_data/tree/main/de-12/lab5)

### Задачи

### Инструменты
