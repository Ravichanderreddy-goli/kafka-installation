# kafka-installation

# kafka-commands

- First open powershell in C:\kafka_2.13-2.7.0 folder
- Open Powershell window for each process

Window 1 - Run Zookeeper Service (keep window open)
```
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```
Window 2 - Run Kafka Service (keep window open)
```
.\bin\windows\kafka-server-start.bat .\config\server.properties
```
Window 3 (temporary) - Execute One-Time Commands - create, list, delete topics 
```
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic my-list
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list
```
Window 4 - Run Kafka Producer (will provide a > prompt for writing messages)
```
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic my-list
```
Window 5 - Run Kafka Consumer (to show messages from the beginning)
```
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic my-list --from-beginning
```
