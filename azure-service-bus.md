### [Azure Service Bus](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-messaging-overview)
Microsoft Azure Service Bus is a fully managed enterprise integration message broker. Service Bus can decouple applications and services. Service Bus offers a reliable and secure platform for asynchronous transfer of data and state.

Connect on-premises and cloud-based applications and services to implement highly secure messaging workflows.

Some common messaging scenarios are:

- Messaging. Transfer business data, such as sales or purchase orders, journals, or inventory movements.
- Decouple applications. Improve reliability and scalability of applications and services. Client and service don't have to be online at the same time.
- Topics and subscriptions. Enable 1:n relationships between publishers and subscribers.
- Message sessions. Implement workflows that require message ordering or message deferral.

#### Components
- Queues
	- Single Sender and Single receiver
- Topics
	- Single sender and multiple receivers

#### Azure service bus in action
- Service bus Namespace: A namespace is a container, with a unique fully qualified domain name, for queues, topics, and relays. You must start by creating the namespace.
	- Each namespace has primary and secondary shared access signature encryption keys
	- Service Bus Queue
	- Service Bus topics and subscriptions
- Use shared access signatures in message publisher and subscriber to connect to service bus queue.


### Service Bus Explorer
https://github.com/paolosalvatori/ServiceBusExplorer
https://docs.microsoft.com/en-us/azure/developer/java/spring-framework/configure-spring-boot-starter-java-app-with-azure-service-bus
