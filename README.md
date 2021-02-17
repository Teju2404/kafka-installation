# Kafka - Installation

1. [Download](https://apache.claz.org/kafka/2.7.0/kafka_2.13-2.7.0.tgz)
### To extract the downloaded file.Follow the below commands using GitBash
1. $ tar -xzf kafka_2.13-2.7.0.tgz
1. $ cd kafka_2.13-2.7.0

### To start the Kafka Environment
### Kafka-Commands

- Use a different PowerShell as Administrator window for each process.  You may minimize windows, but they must remain  open to keep the processes running.

Window 1 - Run Zookeeper Service  (keep window open)
```
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```
Window 2 - Run Kafka Service (keep window open)
```
.\bin\windows\kafka-server-start.bat .\config\server.properties
```
Window 3 (temporary) - Execute One-Time Commands - create, list, delete topics 
```
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic bearcat-messages

.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list
```
Window 4 - Run Kafka Producer (will provide a > prompt for writing messages)
```
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic bearcat-messages
```
Type your messages in this powershell window.

Window 5 - Run Kafka Consumer (to show messages from the beginning)
```
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic bearcat-messages --from-beginning
```
