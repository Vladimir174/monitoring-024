# monitoring-024
Системы агрегации сообщений Logstash/Vector // ДЗ

**Домашнее задание**

Преобразование входящих сообщений с помощью Logstash и Vector

Цель:
Установить и настроить Logstash и Vector таким образом, чтобы происходил парсинг входящих сообщений.


Описание/Пошаговая инструкция выполнения домашнего задания:
Используйте тот же стенд из 2х VM как в предыдущем задании:

Установите Logstash на виртуальную машину с Elasticsearch. Перенастройте отправку логов в него. В Logstash добавьте парсинг логов при помощи grok фильтр (Filebeat пусть при этом шлет сырые данные).
Вместо Logstash установите и настройке Vector с аналогичным парсингом логов при помощи VRL.


1. Установлен Logstash рядом с Elasticsearch.

   конфиг [logstash](https://github.com/Vladimir174/monitoring-024/blob/main/logstash.yml)

   конфиг [Elasticsearch](https://github.com/Vladimir174/monitoring-024/blob/main/elasticsearch.yml)

3. На другой ВМ Filebeat перенастроен на отправку логов в него.

   конфиг [filebeat](https://github.com/Vladimir174/monitoring-024/blob/main/filebeat.yml)

   Filebeat шлет данные в logstash, затем применяется фильтр для лога mariadb, конфиг с именем [mariadb-filter](https://github.com/Vladimir174/monitoring-024/blob/main/mariadb-filter.conf). 

![image](https://github.com/user-attachments/assets/2cf73a04-c30e-44dc-9f99-7535c3f3679c)

3. Установлен и настроен Vector.

