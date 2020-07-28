### [Azure API Management](https://docs.microsoft.com/en-us/azure/api-management/)

APIM make it easey to expose your limited data and features to public internet without focusing on secondry tasks like security etc. It makes easy to manage and control over API end points.

Azure API Management acts as a gateway between your web APIs and the public Internet. An Azure API gateway is an instance of the Azure API management service.

For developers, API Management provides a range of benefits.

- API documentation
  - API versioning
  - based on Open standards like open API
 - Rate limiting access
 - Health monitoring
 - Modern formats like JSON
  - Exchange formats on demand
 - Connections to any API
  - Centeralized API
 - Analytics
 - Security

#### Pricing 
A scale unit enables you to scale up a service. The more scale units you have, the more you can scale up the service.

- Developer
- Basic
- Standard
- Premium
- Consumption
#### API frameworks
- Blank API	You can import an API with a blank API definition. You then manually specify all the required parameters.
- Open API	Open API is a specification that documents all the endpoints and operations for RESTful APIs, and all input and output parameters. OpenAPI was originally called Swagger.
- WADL	Web Application Description Language is an XML description of HTTP-based web services. It is a simpler format and more lightweight than WSDL.
- WSDL	Web Service Description Language is an XML description of any network service, not just HTTP.
- Logic App	Logic apps are used to orchestrate and automate workflows and integrations with various data sources.
- API App	An API hosted within an API app service in Azure.
- Function App	Server
#### Policies
API Management policies are configurable modules that you can add to APIs to change their behaviors. Policies can do things like cache responses, transform documents and values, call webhooks for notification or audit purposes, and retry requests after transient failures.

Policies provide powerful capabilities to change the behavior of an API through configuration. They exist as a collection of statements that are executed sequentially on the request or response of an API.

Popular configurations include:

- Conversion from XML to JSON
- Call rate limiting to restrict the number of incoming calls.
- Setting inbound and outbound headers

In Azure API Management, policies execute at four different times:

- Inbound. These policies execute when a request is received from a client.
- Backend. These policies execute before a request is forwarded to a managed API.
- Outbound. These policies execute before a response is sent to a client.
- On-Error. These policies execute when an exception is raised.
#### Product
A product is a collection of APIs. You can assign APIs to more than one product. 

> A subscription key is used to restrict access to an API.

