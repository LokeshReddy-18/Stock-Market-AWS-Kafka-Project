# Stock-Market-AWS-Kafka-Project
<img width="841" alt="Screenshot 2024-07-27 at 8 00 12 PM" src="https://github.com/user-attachments/assets/b8728ce4-068a-443b-a4ce-253274d5b9c6">


## Overview


A Kafka cluster running on an EC2 instance to stream stock market data.
A Python script running on an AWS SageMaker notebook to consume data from Kafka and upload it to an S3 bucket.
AWS Glue crawlers to catalog the data in the S3 bucket.
AWS Athena to query and analyze the data.


## Components
Kafka Cluster: Deployed on AWS EC2 for streaming data.       
AWS EC2: Hosts the Kafka server.         
SageMaker Notebook: Consumes Kafka messages, processes them, and uploads them to S3.             
Amazon S3: Stores the processed data.            
AWS Glue: Crawls the data in S3 to create tables.              
AWS Athena: Provides interactive querying of the data stored in S3.       



## Kafka Set Up on EC2

**Install Java:**

```bash
sudo yum install java-11-openjdk
```

**Download and Extract Kafka:**

```bash
wget https://downloads.apache.org/kafka/3.3.1/kafka_2.12-3.3.1.tgz
tar -xzf kafka_2.12-3.3.1.tgz
cd kafka_2.12-3.3.1
```

**Start Zookeeper Server:**

```bash
bin/zookeeper-server-start.sh config/zookeeper.properties
```

**Start Kafka Server:**

```bash
bin/kafka-server-start.sh config/server.properties
```

**Create Kafka Topic:**

```bash
bin/kafka-topics.sh --create --topic stock_market --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1
```

### Producer and Consumer Codes on Repository

## Conclusion    

This project sets up a comprehensive data pipeline for real-time stock market data using Kafka, AWS services, and provides mechanisms for data analysis using AWS Glue and Athena. Ensure all components are correctly configured and permissions are set to facilitate smooth data flow and analysis.
