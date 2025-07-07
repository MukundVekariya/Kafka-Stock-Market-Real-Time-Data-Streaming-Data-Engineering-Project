# Kafka-Stock-Market-Real-Time-Data-Streaming-Data-Engineering-Project

## Introduction
To enhance my skills in real-time data processing and technologies like Kafka, I conducted an end-to-end Data Engineering project focusing on real-time stock market data analysis. This project utilizes a diverse tech stack, including Python, AWS, Apache Kafka, Glue, Athena, and SQL, to demonstrate the ingestion, processing, and analysis of real-time stock market data.

## Architecture

![Project Architecture Diagram](Architecture.jpg)

## Technology Used
- **Programming Language:** Python
- **Amazon Web Services (AWS):**
  - S3 (Simple Storage Service)
  - Athena
  - Glue Crawler
  - Glue Catalog
  - EC2
- **Apache Kafka**

## Dataset Used
The dataset used for this project is available at:
[Stock Market Dataset (indexProcessed.csv)](https://github.com/darshilparmar/stock-market-kafka-data-engineering-project/blob/main/indexProcessed.csv)

## Kafka Setup Instructions

### Install Kafka version - 3.7.2
```sh
wget https://downloads.apache.org/kafka/3.7.2/kafka_2.12-3.7.2.tgz

sudo yum install java-1.8.0-openjdk  # Install Java
cd kafka_2.12-3.7.2
```

### Start Zookeeper
```sh
bin/zookeeper-server-start.sh config/zookeeper.properties
```

### Start Kafka Server
```sh
export KAFKA_HEAP_OPTS="-Xmx256M -Xms128M"
bin/kafka-server-start.sh config/server.properties
```

### Create Kafka Topic
```sh
bin/kafka-topics.sh --create --topic demo_test --bootstrap-server {your IP address here}:9092 --replication-factor 1 --partitions 1
```

### Start Producer
```sh
bin/kafka-console-producer.sh --topic demo_test --bootstrap-server {your IP address here}:9092
```

### Start Consumer
Duplicate the session & enter in a new console:
```sh
bin/kafka-console-consumer.sh --topic demo_test --bootstrap-server {your IP address here}:9092
```