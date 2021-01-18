Apache Flink
--------------
# To start local cluster :
start-cluster.sh
# To stop local cluster :
stop-cluster.sh

Apache Kafka
----------------
#Start zookeeper :
zookeeper-server-start.sh $KAFKA_HOME/config/zookeeper.properties

#Start broker:
kafka-server-start.sh $KAFKA_HOME/config/server.properties

# Create topic:
kafka-topics.sh --zookeeper localhost:2181 --create --topic <topic name> --partiotions 1 --replication-factor 1

# List all topics:
kafka-topics.sh --zookeeper localhost:2181 --list

# Publish messages through console producer:
kafka-console-producer.sh --broker-list localhost:9092 --topic <topic name>

# Consume messages through console consumer:
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic <topic name>

# Consume messages through console consumer (from beginning):
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic <topic name> --from-beginning

# Submitting flink application from command line locally
flink run -c <main class with package name> <application jar file>