https://github.com/Yolean/confluent-quickstart-kubernetes

- https://hub.helm.sh/charts/incubator/schema-registry
- https://github.com/helm/charts/tree/master/stable/schema-registry-ui?ref=kubedexcom

https://github.com/strimzi/strimzi-kafka-operator

- https://github.com/tchiotludo/kafkahq
- https://github.com/spotguides/kafka/tree/master/.banzaicloud/charts/kafkahq

----
# Apache Kafka
* https://kafka.apache.org/documentation/
* https://sookocheff.com/post/kafka/kafka-in-a-nutshell/
* https://github.com/infoslack/awesome-kafka
```
Consumers and Consumer Groups

Consumers read from any single partition, allowing you to scale throughput of message consumption in a similar fashion to message production. Consumers can also be organized into consumer groups for a given topic — each consumer within the group reads from a unique partition and the group as a whole consumes all messages from the entire topic. If you have more consumers than partitions then some consumers will be idle because they have no partitions to read from. If you have more partitions than consumers then consumers will receive messages from multiple partitions. If you have equal numbers of consumers and partitions, each consumer reads messages in order from exactly one partition.
```

## Kafka vs. Pulsar
- https://medium.com/@bhagwanssoni/apache-pulsar-is-it-a-kafka-killer-a7538afedd0b
- https://stackoverflow.com/questions/46048608/what-are-the-advantages-and-disadvantages-of-kafka-over-apache-pulsar
#### Kafka vs Pulsar
  
- https://streaml.io/blog/pulsar-streaming-queuing
- https://jack-vanlightly.com/sketches/2018/10/2/kafka-vs-pulsar-rebalancing-sketch
- https://conferences.oreilly.com/strata/strata-ca-2019/public/schedule/detail/72853
- https://kafkaesque.io/7-reasons-we-choose-apache-pulsar-over-apache-kafka/



## Mirroring (replication)
* https://github.com/salesforce/mirus
* MirrorMaker
* uReplicator

## Cluster topology (Hierarchy)
* https://events.linuxfoundation.org/wp-content/uploads/2017/11/Building-Scalable-and-Extendable-Data-Pipelines-For-Call-Of-Duty-Games-Lessons-Learned-Yaroslav-Tkachenko.pdf
* https://www.slideshare.net/kawamuray/multitenancy-kafka-clusters-for-everyone-at-line
* https://www.confluent.io/kafka-summit-sf17/multitenant-multicluster-and-hieracrchical-kafka-messaging-service

## Docker

```
git clone https://github.com/youngwookim/kafka-stack-docker-compose.git

git tag -l
v3.2.0
v3.2.1
v3.3.0
v3.3.1
v4.0.0
v4.1.0
v4.1.2
v5.0.0
v5.1.0

git checkout tags/v4.1.2
```

```
docker-compose -f zk-single-kafka-single.yml up
docker-compose -f zk-single-kafka-single.yml down

or

docker-compose -f full-stack.yml up
docker-compose -f full-stack.yml down

Single Zookeeper: $DOCKER_HOST_IP:2181
Single Kafka: $DOCKER_HOST_IP:9092
Kafka Schema Registry: $DOCKER_HOST_IP:8081
Kafka Schema Registry UI: $DOCKER_HOST_IP:8001
Kafka Rest Proxy: $DOCKER_HOST_IP:8082
Kafka Topics UI: $DOCKER_HOST_IP:8000
Kafka Connect: $DOCKER_HOST_IP:8083
Kafka Connect UI: $DOCKER_HOST_IP:8003
Zoonavigator Web: $DOCKER_HOST_IP:8004

```

## Benchmark
* https://gist.github.com/saurabhmishra/6ed428be4c00003dd926

## Kafka Streams (+ Avro)
* https://kafka.apache.org/documentation/streams/
* http://kafka.apache.org/11/documentation/#streamsconfigs
* https://kafka.apache.org/documentation/streams/developer-guide/
* https://docs.confluent.io/current/streams/index.html
* https://github.com/confluentinc/kafka-streams-examples/blob/4.1.1-post/src/main/java/io/confluent/examples/streams/WikipediaFeedAvroExample.java
* https://www.slideshare.net/sap1ens/kafka-streams-the-easiest-way-to-start-with-stream-processing
* https://datamelt.weebly.com/blog/ruleengine-with-kafka-streams
* https://codelook.com/versatile-streaming-data-processing-using-kafka-streams-76b32dbe8ef9
  * https://github.com/robvadai/kafka-streams-bootstrap
* https://github.com/jaceklaskowski/mastering-kafka-streams-book
* https://www.manning.com/books/kafka-streams-in-action

* https://www.confluent.io/blog/data-reprocessing-with-kafka-streams-resetting-a-streams-application/

## Tuning Kafka
* https://kafka.apache.org/documentation/#configuration
* https://community.hortonworks.com/articles/80813/kafka-best-practices-1.html

## KSQL
* https://github.com/confluentinc/ksql
* https://github.com/mmolimar/ksql-jdbc-driver
* KSQL + Avro, https://www.confluent.io/blog/ksql-december-release

## Kafka connect
* https://github.com/Landoop/stream-reactor

## Kafka Consumer client
* https://www.confluent.io/blog/tutorial-getting-started-with-the-new-apache-kafka-0-9-consumer-client/
* Kafka Clients (at-most-once, at-least-once, exactly-once and Avro Client), https://medium.com/@ajmalbabu/kafka-0-9-0-clients-db1f43257d30
* Scalability of Kafka Messaging using Consumer Groups, http://blog.cloudera.com/blog/2018/05/scalability-of-kafka-messaging-using-consumer-groups/

## Kafka REST Proxy
* https://github.com/confluentinc/kafka-rest
* https://github.com/gamechanger/kafka-rest : Async Python client for Kafka REST proxy
* https://github.com/bergundy/python-kafka-rest-client

## Kafka, Spark and Avro Integration
- http://www.hongyusu.com/amt/spark-streaming-kafka-avro-and-registry.html
- https://github.com/opencore/kafka-spark-avro-example
- https://github.com/simplesteph/kafka-avro-course-udemy
- https://wecode.wepay.com/posts/kafka-avro-client

## Kafka Schema Registry
- https://github.com/confluentinc/schema-registry
- https://github.com/Landoop/schema-registry-ui
- https://dzone.com/articles/kafka-avro-serialization-and-the-schema-registry
- http://cloudurable.com/blog/kafka-avro-schema-registry/index.html
- https://www.confluent.io/blog/put-several-event-types-kafka-topic/
- https://www.ctheu.com/2017/03/02/serializing-data-efficiently-with-apache-avro-and-dealing-with-a-schema-registry/
```
The compatibility checks value is one of the following:

NONE - don’t check for schema compatibility
FORWARD - check to make sure last schema version is forward compatible with new schemas
BACKWARDS (default) - make sure new schema is backwards compatible with latest
FULL - make sure new schema is forwards and backwards compatible from latest to new and from new to latest
```
- https://github.com/cricket007/schema-registry-transfer-smt
- https://github.com/rayokota/schema-registry-browser
- https://www.slideshare.net/JeanPaulAzar1/kafka-and-avro-with-confluent-schema-registry

https://github.com/farmdawgnation/registryless-avro-converter

## Unit Test
- https://github.com/charithe/kafka-junit
- https://github.com/chbatey/kafka-unit
- https://github.com/salesforce/kafka-junit
- https://github.com/Landoop/kafka-testing
- https://gist.github.com/benstopford/49555b2962f93f6d50e3
- https://groups.google.com/forum/#!topic/confluent-platform/oOZ852q8aB4

https://github.com/confluentinc/kafka-streams-examples/blob/4710dbf7017666157ce01de4108b57da41399c28/src/test/java/io/confluent/examples/streams/kafka/EmbeddedSingleNodeKafkaCluster.java

```
<dependency>
			<groupId>io.confluent</groupId>
			<artifactId>kafka-streams-examples</artifactId>
			<version>4.1.0</version>
			<!-- Required for e.g. schema registry's RestApp -->
			<classifier>tests</classifier>
			<scope>test</scope>
		</dependency>
```

## Kafka OPS
- https://kafka.apache.org/documentation/#operations
```
1. Alter configs for Kafka topics
# List topics
kafka-topics.sh --list --zookeeper localhost:2181

# Describe the topic
kafka-configs.sh --zookeeper localhost:2181 --entity-type topics --entity-name TOPIC_NAME

# The default retention time is 24 hours (86400000 millis)
kafka-configs.sh --zookeeper localhost:2181 --entity-type topics --entity-name TOPIC_NAME --alter --add-config retention.ms=5184000000


```

https://docs.confluent.io/current/kafka/operations.html

## Monitoring
- https://github.com/linkedin/cruise-control
- https://github.com/yahoo/kafka-manager
- https://github.com/linkedin/Burrow
- https://github.com/linkedin/kafka-monitor

## Tools
- https://github.com/BetterCloud/kadmin

## Tips
zookeeper:
```
zookeeper.connect=zk1:2181,zk2:2181,zk3:2181/kafka
```

## Examples
- https://github.com/confluentinc/examples
- https://github.com/gwenshap/kafka-examples
- https://github.com/simplesteph/kafka-avro-course-udemy
- https://github.com/confluentinc/kafka-streams-examples

## Cheatsheet
- http://ronnieroller.com/kafka/cheat-sheet