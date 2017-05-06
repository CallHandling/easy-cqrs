# easy-cqrs (Work in planning phase)

A library built on akka, kafka and cassandra to make distributed CQRS simple. 

The  plan is to create a trait to extend any of the actors which will output all events to kafka and store archive events to cassandra (will rely on protobuf definitions for internal event types). 

You will then be able to define read tables (initially for cassandra) in a simple definition file. All the code to syncronise the processing of data between batch job and streaming jobs will be managed by the library. You will just see the new table populated with data. 

The library is built on Kafka Connect and Kafka Streams meaning that the read table definitions wil use the Kafka Streams API to generate from the event types input. You will also be able to join other other ktables and kstreams that exist in your program. 

Finally we will generate interfaces to read the read table. 
