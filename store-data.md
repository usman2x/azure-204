### Azure services to store data
In order to use right service in azure for data storage you need to classify your data in different models and types. 
Data could have different shape and size. Data could be relational, non relational, JOSN, unstructured, graphical form or any other type of data. According to type and model of
data we choose right and specific azure service so that we can leverge best outcome from the service. That's why azure designed services to cater specific data needs.

### Classification of Data
1. Structured

This Data some time refered as relationla data and stored in the form of database tables with rows and columns that adheres strict schema.

2. Semi-structured

This type of data also known as non-relational or NoSQL data. Data store in files using serialization languages.
Some common serialization languages are.

- XML
- JSON
- YAMAL

3. Unstructured

### Data transactions
A transaction is a logical group of database operations that execute together.

Transactions are often defined by a set of four requirements, referred to as ACID guarantees. ACID stands for Atomicity, Consistency, Isolation, and Durability:

- Atomicity means a transaction must execute exactly once and must be atomic; either all of the work is done, or none of it is. Operations within a transaction usually share a common intent and are interdependent.
- Consistency ensures that the data is consistent both before and after the transaction.
- Isolation ensures that one transaction is not impacted by another transaction.
- Durability means that the changes made due to the transaction are permanently saved in the system. Committed data is saved by the system so that even in the event of a failure and system restart, the data is available in its correct state.

#### Transaction Data bases
1. OLTP (Online Transaction Processing)
2. OLAP (Online Analytical Processing)

### How to choose right data service
1. Classification of data
2. Operations you will perform on data
3. Latancy and throughput requirements
4. Transactional support requirements

### Azure services for data storage
![Azure services for data storage](https://docs.microsoft.com/en-us/learn/modules/create-azure-storage-account/media/2-azure-storage.png)
