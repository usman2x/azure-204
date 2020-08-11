### Azure Cache for Redis
> Redis(REmote DIctionary Server) is an open source (BSD licensed), in-memory data structure store, used as a database, cache and message broker. 
Azure Cache for Redis can be used as a distributed data or content cache, a session store, a message broker, and more. It can be deployed as a standalone or along side with other Azure database service, such as Azure SQL or Cosmos DB.

Data in Redis is stored in nodes and clusters.

- Nodes are a space in Redis where your data is stored.
- Clusters are sets of three or more nodes your dataset is split across. Clusters are useful because your operations will continue if a node fails or is unable to communicate to the rest of the cluster.

Redis caching architecture is how we distribute our data in the cache. Redis distributes data in three major ways:

- Single node
- Multiple node
- Clustered

### Features
- Transactions: Transactions in Redis work by queueing multiple commands to be executed as a group
- Data Expiration: Redis store data in memory not on hard disk, so we have limited memory as compare to hard disk hence data must be short lived and store only data that has most importance.
- Eviction policy: An eviction policy is a plan that determines how your data should be managed when you exceed the maximum amount of memory available. For example, using an eviction policy, you could tell Azure Cache for Redis to delete a random key to make room for the new data being inserted. There are six different eviction policies provided by Azure Cache for Redis.

  - noeviction: No eviction policy. Returns an error message if you attempt to insert data.
  - allkeys-lru: Removes the least recently used key.
  - allkeys-random: Removes a random key.
  - volatile-lru: Removes the least recently used key out of all the keys with an expiration set.
  - volatile-ttl: Removes the key with the shortest time to live based on the expiration set for it.
  - volatile-random: Removes a random key that has an expiration set.
- Cache Aside Pattern: The cache-aside pattern dictates that when you need to retrieve data from a data source, like a relational database, you should first check for the data in your cache. If the data is in your cache, use it. If the data is not in your cache, then query the database, and when you're returning the data back to the user, add it to your cache.

### Considerations for using the cache-aside pattern
- Lifetime: For cache-aside to be effective, make sure that the expiration policy matches the access frequency of the data. Making the expiration period too short can cause applications to continually retrieve data from the data store and add it to the cache.

- Evicting: Caches have a limited size compared to typical data stores, and they'll evict data if necessary. Make sure you choose an appropriate eviction policy for your data.

- Priming: To make the cache-aside pattern effective, many solutions will prepopulate the cache with data that they think will be accessed often.

- Consistency: Implementing the cache-aside pattern doesn't guarantee consistency between the data store and the cache. Data in a data store can be changed without notifying the cache. This can lead to serious synchronization issues.
  
#### Related services
1. Front Door
2. CDN

#### Concepts
> Redis does not support transaction rollbacks.
> The length of a Redis key impacts the performance of lookup time
> Redis works best with data that is 100 K or less. Splitting and storing larger data with multiple keys will reduce network latency and out-of-memory issues.


