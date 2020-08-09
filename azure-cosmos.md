
### Three V's of Data
- Velocity: How fast is Date being processed
- Volume: How large the Data is
- Variety: Relational, Structured, Unstructured

### What is Cosmos DB
Cosmos DB is an organizational entity for databases. Each Azure Cosmos DB account is associated with one of the several data models Azure Cosmos DB supports.
Azure Cosmos DB provides five APIs to suit the needs of your application: SQL (document database), Gremlin (graph database), MongoDB (document database), Azure Table, and Cassandra, each of which currently requires a separate account.

### Best practices
- When creating an account, choose an ID that is meaningful to you; it is how you identify your account. 
- Create the account in the Azure region that's closest to your users to minimize latency between the datacenter and your users.

### Pricing
Create, read, update, delete operations required to provision througput (Request units) first. Througput can be provisioned at Database level or container level. Throuput provisined at databse level inherits to container level until unless througput is not provisioned at container level specifically.
Azure measures cosmos db throughput using request units (RUs), so the unit of measure is request units per second (RU/s). 
in nutshell `RUs is a currency that is required to perform any CRUD operation on cosmos DB`.
Before provisioning througput you have to identify your need, how many operation you are going to perfrom. How much RUs a simple opertaion or query consumes. You can obtain the request unit charge for any operation on your Azure Cosmos DB containers. Multiply the number of consumed RUs of each operation by the estimated number of times each operation (write, read, update, and delete) will be executed per second.
You provision the number of RUs on a per-second basis and you can change the value at any time in increments or decrements of 100 RUs.

Request Unit considerations
- Item size: As the size of an item increases, the number of RUs consumed to read or write the item also increases.
- Item indexing: By default, each item is automatically indexed. Fewer RUs are consumed if you choose not to index some of your items in a container.
- Item property count: Assuming the default indexing is on all properties, the number of RUs consumed to write an item increases as the item property count increases.
- Indexed properties: An index policy on each container determines which properties are indexed by default. To reduce the RU consumption for write operations, limit the number of indexed properties.
- Data consistency: The strong and bounded staleness consistency levels consume approximately two times more RUs on read operations when compared to that of other relaxed consistency levels.

- Query patterns: The complexity of a query affects how many RUs are consumed for an operation. Factors that affect the cost of query operations include:

  - The number of query results
  - The number of predicates
  - The nature of the predicates
  - The number of user-defined functions
  - The size of the source data
  - The size of the result set
  - Projections

-Script usage: As with queries, stored procedures and triggers consume RUs based on the complexity of their operations. As you develop your application, inspect the request charge header to better understand how much RU capacity each operation consumes.

> At the lowest level, Azure Cosmos DB stores data in atom-record-sequence (ARS) format. The data is then abstracted and projected as an API
> Azure Cosmos DB offering you five different consistency levels: strong, bounded staleness, session, consistent prefix, and eventual.

### Cosmos DB partition
Data stored in collections are distributed across partitions based on partition key. A partition key is property of a document. The Azure Cosmos DB throughput you've configured is divided evenly among partitions. A partition key design that doesn't evenly distribute throughput requests can create hot partitions
