### Communication between different services or components of application (Distributed Applications)

We will discuss how can we leverege azure services to communicate between different components or services of application.

There are different types of communication available for services to talk each other, synchronous or asynchronous. 

HTTP/HTTPS is request/response communication model. It is a synchronous protocol to communicate between services, you may wonder even we can use HTTP/HTTPS send requests 
in asynchronous way, yes, but this asychronous behaviour in your code and protocol is still synchronous. In this type of communication sender expects quick response from receiver. 
This type of communication usually we use in real time applications. For example a developer is searching "Java hello world example" query in blog website would expect results 
in blazing fast speed.

AMPQ is asynchronous protocol for sending messages from one service to another service. Sender usually does not wait for message response from receiver, it sends message to 
queue or message broker.

Microservices also uses single receiver or multiple receivers communication between services. In multiple receiver type of communication there are multiple services that can 
receive the single request or message or event. This type of communication also known as publisher/subscriber. Publisher sends the message to service bus and receivers/consumers
from different services subscribe to topics of the service bus can receive the same message.

The commnication between microservies should be
1) Reliable
2) Durable
3) Scalable

Before we choose azure services for distrubute application we need to understand what type of communication do our services need. What they produce to communicate between the
services, either it is simple request or a message or an event. To understand the difference between message and event. 
> The difference being that messages are directed, events are not — a message has a clear addressable recipient while an event just happen for others (0-N) to observe it.

For example Ali is using debit card to do transactions on POS terminal, after transaction done, Ali needs SMS alert and email from bank to the transaction. So this type
of communication use message which contains all transaction information and payment processor must process this message.

Event based communication usually held for logging or to track Change Data capture (CDC). 

If Sender components requires producer to process the request in particular way then use message based style othervise use event driven style.

Azure Service
1) Azure Queue Storage
2) Azure Service Bus
3) Azure Event Grid
4) Azure Event Hub

In General there are two types of asynchronous communication.

1. Message base communication
2. Event base communication

#### Decide between messages and events

- Messages: In the terminology of distributed applications, the defining characteristic of a message is that the overall integrity of the application may rely on messages being received. 
  - The sender and receiver of a message are often coupled by a strict data contract.
  - 1-1
  - 1-N (Filters, Subscribers)
- Events: An event triggers a notification that something has occurred. Events are "lighter" than messages and are most often used for broadcast communications.
  - 1-N (Optional)
  - The event may be sent to multiple receivers, or to none at all
  - The publisher of the event has no expectation about the action a receiving component takes
  
### Message Delivery Options
- At-least-one-delivery 
- At-most-one-delilvery
- First-in-First-out
- Transactionla support
