## Redis
1. Redis is a NoSQL and multi-model database.
2. There are 4 major types of NoSQL databases
	- Key/Value based
	- Column based
	- Document based
	- Graph based

### Database,memory and persistence
1. No formal databse creation step with Redis
2. No table creation step neccessary either.
3. SET command is used to create data within the current database.

### Redis Use Cases
Redis has the capability to meet user expectations for performance and features.
1. Personlization with session management: By nature session related data must be readily available with low latency to meet performance requirements that users expect.
2. Social Apps: Several features of Redis makes implementation of soical app features possible
	a. Intelligent Caching
	b. Publish Subscribe pattern for incoming data.
	c. Job and Queue management 
	d. Built-in analytics
	e. Native JSON handling
3. Search: Allowing users to search data while providing high performance is even more difficult.

### Redis in Real World (Example in a e-commerce)
- **Caching**: Redis for caching data between the application and the backend data store, such as another relational or NoSQL database.
- **Large Datasets**: Recommendations and Customers Analytics can be done in real time.
- ** Full-text Search**: RediSearch module can be used for this as it can work upto 50% faster than stand-alone search engine products and includes features like scoring, filtering and query expansion.
- **Geospatial and time-series data**: Excellent choice for geospatial and time series data.These data types might be used for location based recommendations and promotions. Another usecase for these data-types is collection of data from IoT devices.
- **Messaging/queueing**: For handling fast-moving data.Data that is generated rapidly and needs to be analyzed and processed.It can be collected, streamed and ingested by Redis using its native publish/subscribe mechanism.

### Using Multi-Model Redis
A multi-model database like Redis enables the data to be represented for multiple use cases simultaneously. This means that the data can be used in the manner most appropriate for the application.

### Redis Data Models:
- Data is stored in Redis using Keys.
- They can be anything beause they're binary safe

### Primary Data models in Redis
- Strings and Hashmaps
- Lists 
- Sets
- Hashes
- Sorted Sets
- HyperLogLogs

### Patterns and Data Structures
1. **Publisher/Subscirber**: Publisher creates a ley/value pair and zero or more subscribers recieve messages.
2. **Geospatial**: Geospatial indexing is a common pattern used for encoding data that relies on lattitude and longitude. There are built-in funtions specific to this type of data once they are added/
### Streams 
Similar to the pub.sub model but with even more power and subscriber has the ablility to get the old messages from the publisher as the publisher can store the messages as opposed to in the pub/sub model.

## Modules 
They further enhance tje capablility of Redis:
Three such modules are:
1. Redis Graph: Implements a Graph database in Redis
2. RediSearch
3. Redis Time Series


