### Azure functions
Azure function is a service of azure to write business logic(small piece of code aka functions) in different programming lanagauages supported and deploy as a function to perfrom or execute on the basis of different triggers without having to provision or manage infrastructure.

Azure Functions can be triggered by the events from other services.
- HTTPTrigger
- TimerTrigger
- CosmosDBTrigger
- BlobTrigger
- QueueTrigger
- ServiceBusTopicTrigger
- EventHubTrigger
- ServiceBusQueueTrigger

#### Components
- Function Proxies
- Staless functions
- Durable (Stateful) Functions

#### Durable functions
Durable Functions is an extension of Azure Functions that lets you write stateful functions in a serverless compute environment.
The primary use case for Durable Functions is simplifying complex, stateful coordination requirements in serverless applications. The following sections describe typical application patterns that can benefit from Durable Functions:

- Function chaining
- Fan-out/fan-in
- Async HTTP APIs
- Monitoring
- Human interaction
- Aggregator (stateful entities)

#### Pricing
- Consumption plan
- Premium plan
- App Service plan
