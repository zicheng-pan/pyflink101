## Intro
this project is for flink sql demo.

## Ecosystem on Apache Flink
![](readmeimg/flinkarch.png)

## [Storage](https://nightlies.apache.org/flink/flink-docs-master/docs/connectors/table/overview/) 
Apache Flink has multiple options from where it can Read/Write data. Below is a basic storage list −
<ol>
<li>DFS (Hadoop Distributed File System)</li>
<li>Local File System</li>
<li>S3</li>
<li>RDBMS (MySQL, Oracle, MS SQL etc.)</li>
<li>MongoDB</li>
<li>HBase</li>
<li>Apache Kafka</li>
<li>Apache Flume</li>
</ol>

## Generally Flink job component
![img.png](readmeimg/flinkcodeprocess.png)

## Relation between JobManager & TaskManager
![img.png](readmeimg/jobmanagerandtaskmanager.png)

## Slot in TaskManager
![img.png](readmeimg/slot_sharing.svg)


## Platform environment
make sure installed the applications below before running this project <br>
<b>1. [kafka.](https://kafka.apache.org/downloads) <br></b>
<b>2. [flink.](https://www.apache.org/dyn/closer.lua/flink/flink-1.17.0/flink-1.17.0-bin-scala_2.12.tgz)</b> If submitting job on flink locally, make sure you cloud open the 
flink manage website on http://localhost:8081/ <br>
<b>3. if run python job on flink please install flink in python intepretor by ``python -m pip install apache-flink`` </b>


## Kafka topic operation

### 1. launch zookeeper locally

   <code>sudo bin/zookeeper-server-start.sh -daemon config/zookeeper.properties</code>
### 2. launch kafka locally  
``bin/kafka-server-start.sh config/server.properties``
### 3. create a kafka topic
``bin/kafka-topics.sh --bootstrap-server localhost:9092 --partitions 2 --create --topic template001``
### 4. produce data to kafka topic
``bin/kafka-console-producer.sh --bootstrap-server localhost:9092 --topic source_topic --producer.config config/producer.properties``
### 5. consume data from kafka topic
``bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --from-beginning --topic sink_topic``


### for python Closure Demo using in UDF for define user function for sql

### udf demo

## PyFlink application for KDA in AWS
here is a [video](https://www.youtube.com/watch?v=00JgwB5vJps) supplying introduction and sample code running in AWS Kinesis Analytics.  
