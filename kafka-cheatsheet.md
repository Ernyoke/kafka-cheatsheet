# Kafka Cheatsheet

## Topics

### Createa a topic

```
kafka-topics --zookeeper 127.0.0.1:2181 --topic first-topic --create --partitions 3 --replication-factor 1
```

### List topics

```
kafka-topics --zookeeper 127.0.0.1:2181 --list
```

### Get information about a topic

```
kafka-topics --zookeeper 127.0.0.1:2181 --topic first-topic --describe
```

### Delete a topic

```
kafka-topics --zookeeper 127.0.0.1:2181 --topic first-topic --delete
```

## Producer

### Produce messages

```
kafka-console-producer --broker-list 127.0.0.1:9092 --topic first-topic
```

### Add properties

```
kafka-console-producer --broker-list 127.0.01:9092 --topic first_topic --producer-property acks=all
```

## Consumer

### Consume message

```
kafka-console-consumer --bootstrap-server 127.0.0.1:9092 --topic first-topic
```

### Consume messages from beginning

```
kafka-console-consumer --bootstrap-server 127.0.0.1:9092 --topic first-topic --from-beginning
```

### Groups

```
kafka-console-consumer --bootstrap-server 127.0.01:9092 --topic first-topic --group my-first-application
```

## Consumer groups

### List all groups

```
kafka-consumer-groups --bootstrap-server 127.0.0.1:9092 --list
```

### Get information about the group

```
kafka-consumer-groups --bootstrap-server localhost:9092 --describe --group newgroup
```

### Reset offset

```
kafka-consumer-groups --boostrap-server localhost:9092 --group newgroup --reset-offsets --to-earliest --execute --topic first-topic
```

```
kafka-consumer-groups --boostrap-server localhost:9092 --group newgroup --reset-offsets --shift-by -2 --execute --topic first-topic
```

