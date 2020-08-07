
### [Azure Event Hub](https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-about)

Azure Event Hubs is a big data streaming platform and event ingestion service. It can receive and process millions of events per second. Data sent to an event hub can be transformed and stored by using any real-time analytics provider or batching/storage adapters.

he following scenarios are some of the scenarios where you can use Event Hubs:

- Anomaly detection (fraud/outliers)
- Application logging
- Analytics pipelines, such as clickstreams
- Live dashboarding
- Archiving data
- Transaction processing
- User telemetry processing
- Device telemetry streaming

![Event hub](https://docs.microsoft.com/en-us/learn/modules/enable-reliable-messaging-for-big-data-apps-using-event-hubs/media/2-event-hub-overview.png)

#### Components
- Events: An event is consists of packet of information, can't excced from 1MB.
- Publisher: Any application, entity or device that create the event. It can send event to stream pipeline through AMQP, HTTPS or kafka protocols.
- Subscriber: The application that consumes or receives the event and process.
- Consumer Group: An Event Hub consumer group represents a specific view of an Event Hub data stream.

#### Pricing
There are three pricing tiers for Azure Event Hubs: Basic, Standard, and Dedicated. The tiers differ in terms of supported connections, the number of available Consumer groups, and throughput.
- Basic
- Standard
- Dedicated
#### Concepts
- Throughput units
- Partition:Event Hubs default to 4 partitions. Partitions are the buckets within an Event Hub. Each publication will go into only one partition. Each consumer group may read from one or more than one partition.
- Partition count:  The number of partitions required in an Event Hub (between 2 and 32). The partition count should be directly related to the expected number of concurrent consumers and can't be changed after the hub has been created.
- Message Retention
#### Best practices
- Partitions are ordered sequence of events, 
- Event hub provides partitioned consumer pattern that enables consumer to 
read subset or partition of message stream.
- This pattern enables horizontal scale for event processing
- Partitions can only be specified at the time of namespace creation.

> Dynamic additions of partitions is available only on Dedicated Event Hubs clusters.
> If you use partition key with your producer applications and depend on key hashing to ensure ordering in a partition, dynamically adding partitions isn't recommended.

> We recommend that you balance 1:1 throughput units and partitions to achieve optimal scale. A single partition has a guaranteed ingress and egress of up to one throughput unit. While you may be able to achieve higher throughput on a partition, performance is not guaranteed. This is why we strongly recommend that the number of partitions in an event hub be greater than or equal to the number of throughput units.

- Partitions assignment
	- Direct to partition
	- Partition key
	- Round robin
