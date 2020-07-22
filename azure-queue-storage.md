### [Azure Queue Storage](https://docs.microsoft.com/en-us/learn/modules/communicate-between-apps-with-azure-queue-storage/2-create-the-azure-storage-infrastructure)

Azure Queue storage is an Azure service that implements cloud-based queues. Each queue maintains a list of messages. Application components access a queue using a REST API or an Azure-supplied client library. Typically, you will have one or more sender components and one or more receiver components. Sender components add messages to the queue. Receiver components retrieve messages from the front of the queue for processing.

![Azure Queue Storage](https://docs.microsoft.com/en-us/learn/modules/communicate-between-apps-with-azure-queue-storage/media/2-queue-overview.png)
- Durable: Message is save even if high demand and message processor is slow to process messages
- Reselient
- Scalable
- Byte Array of XML and Json messages

#### Access Tiers

#### Replication
- Locally Redundant Storage (LRS)
- Geo-Redundant Storage (GRS)

#### Performance Tier
- Standard: magnetic drives
- Premium: solid-state drives

##### Access authorization
- Shared Key | Access Key | Account Key
- Shared access signature	
- Azure Active Directory	

> While the total queue size can be up to 500 TB, the individual messages in it can only be up to 64 KB in size (48 KB when using Base64 encoding). If you need a larger payload you can combine queues and blobs – passing the URL to the actual data (stored as a Blob) in the message. This approach would allow you to enqueue up to 200 GB for a single item.

