### [Transient error handling](https://docs.microsoft.com/en-us/azure/architecture/best-practices/transient-faults)
Transient errors (or transient faults) are an error or loss of service that quickly resolves itself.

Transient Errors

- Connectivity: Connectivity could be lost due to interuption or connection broken locally,  DNS or routing errors. It could be due to heavy load on database or data centre goes offline. Build app in a way that it will check first connection if connection becomes unavailabile then it should retry after some time.
- Timeouts: Some opertaions of web based apps require more time to complete, so client has to decide how much time each request time should take to get the response and set the time out time when request will expire. Client also have to check when to give up a request and when to try again. An app should only retry a request if the operation is known to be idempotent.
- Throughput: Mostly cloud based services have policy to set up the Throughput that how many tiemes client will access the service in certain period of time. If client would start more the service will reject the requests. The will be available online ratehr then it crashes or goes offline.
- Service unavailability: Handle this situation gracefully in your client service. You can leverage cache to serve requests temperoray from it. when service is back then go to service for requests.

#### An approach to transient errors
The first step to detect the errors and then classify that error so application able to respond according to error type.
- Transient: It will be self-correcting and that's why retrying the operation could be successful after a short-period of time.
- Permanent: The app can't expect a response from the service, and it should try to get the data from another service or a local cache.
- Terminal: There's nothing useful the app can do without access to the service, and the app should quit.

#### Retry Strategy 
- A defined maximum number of retries
- Specifies an interval between retries - a random or exponentially growing interval is best
- Uses a configuration file to store these parameters so that they can be adjusted easily without any code changes
- Don't keep retrying forever
- Monitor errors in your app using logging : A good set of questions to ask yourself when writing a log message is who, what, why, where, and when.


All the errors will have data that can be used to help diagnose them. An approach to logging these errors should be taken in each of the stages. Logging on the detection of an error, logging on the number of retries, and logging when quitting the app.

#### Retry in code
- Using retry libraries
- Circuit breaker
- Fallback 
- Caching

#### Links
https://docs.microsoft.com/en-us/azure/architecture/best-practices/transient-faults
https://docs.microsoft.com/en-us/azure/architecture/best-practices/retry-service-specific

