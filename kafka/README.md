# General Kafka Commands

* Spin up local zookeeper server
    ```bash
    bin/zookeeper-server-start.sh config/zookeeper.properties
    ```
* Spin up a local kafka server
    ```bash
    bin/kafka-server-start.sh config/server.properties
    ```
  
* Create a topic
    ```bash
    bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic test_topic_dev
    ``` 
* Create a console producer: This will allow you to send messages to the topic
    ```bash
    bin/kafka-console-producer.sh --bootstrap-server localhost:9092 --topic test_topic_dev
    ```  
* Create a console consumer: This will allow you to see messages on a topic
    ```bash
    bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test_topic_dev --from-beginning
    ```

* Pull Messages From Dev Topic:
    ```bash
    bin/kafka-console-consumer.sh --bootstrap-server kafka-broker-dev-us-east-11.cloud.sailpoint.com:9092,kafka-broker-dev-us-east-12.cloud.sailpoint.com:9092,kafka-broker-dev-us-east-13.cloud.sailpoint.com:9092,kafka-broker-dev-us-east-14.cloud.sailpoint.com:9092,kafka-broker-dev-us-east-15.cloud.sailpoint.com:9092,kafka-broker-dev-us-east-16.cloud.sailpoint.com:9092 --topic tenant_usage__echo --from-beginning
    ```  
* List Topics
    ```bash
    bin/kafka-topics.sh --bootstrap-server kafka-broker-dev-us-east-11.cloud.sailpoint.com:9092,kafka-broker-dev-us-east-12.cloud.sailpoint.com:9092,kafka-broker-dev-us-east-13.cloud.sailpoint.com:9092,kafka-broker-dev-us-east-14.cloud.sailpoint.com:9092,kafka-broker-dev-us-east-15.cloud.sailpoint.com:9092,kafka-broker-dev-us-east-16.cloud.sailpoint.com:9092 --list
    ```  
  
  I have been informed that not everyone has permissions to do this command. If this fails you can always use the kafka manager [here](http://kafka-m-820325191.us-east-1.elb.amazonaws.com/clusters/us-east-1-dev/topics/)