This file is intended to compare Application Interfaces (API) between different streaming frameworks. 

We will compare them with regard to following items

1. Blueprint
2. user API vs developer API
3. source and sink API
4. state API
5. multilang supports


All the frameworks allow users to define a blueprint which would be later submitted to the cluster. 

## Storm Topology
 
* Topology is serialized 
* The benefits are it's easy to pass arguments into Spouts and Bolts 
* Spouts and Bolts are both computation abstractions and runnable units

## Spark DStream

* defined in Scala 
* Java API on top of Scala API
* typed
* [transformations](http://spark.apache.org/docs/latest/streaming-programming-guide.html#transformations-on-dstreams)
* `InputDStream` and `Receiver` (both have to be Serializable)
* separated from interpreter
* the runnable unit is `Task`
* KafkaInputDStream and KafkaReceiver is hidden in Scala but not in Java

## Flink DataStream

* defined in Java
* Scala API on top of Java API
* typed
* [transformations](https://ci.apache.org/projects/flink/flink-docs-release-1.0/apis/streaming/index.html#datastream-transformations)
* `SourceFunction` and `SinkFunction` (both have to be Serializable)
* separated from interpreter
* the runnable unit is `StreamTask`

## Gearpump Processor and Stream

provides both Storm-like Processor API and Spark-like DSLs

## What are low level APIs and high level APIs ?

## What are DSLs ?

## Interpreters 

Interpreters are about separating the representation of a computation from the way it is run


## References 

1. http://spark.apache.org/docs/latest/streaming-programming-guide.html
2. https://ci.apache.org/projects/flink/flink-docs-release-1.0/apis/streaming/index.html
3. http://storm.apache.org/tutorial.html
