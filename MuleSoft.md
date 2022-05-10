**MuleSoft**

```
Mule ESB is a lightweight and highly scalable Java-based enterprise service bus (ESB) and integration platform provided by MuleSoft. Mule ESB allows developer to connect applications easily and quickly. Regardless of various technologies used by applications, Mule ESB enables easy integration of applications, enabling them to exchange data.

ESB stands for Enterprise Service Bus which is basically a middleware tool for integrating various applications together over a bus-like infrastructure. Fundamentally, it is an architecture designed to provide a uniform means of moving work among integrated applications. In this way, with the help of ESB architecture we can connect different applications through a communication bus and enable them to communicate without depending on one another.


ESB architecture is to decouple the systems from each other and allow them to communicate in a steady and controllable way. ESB’s implementation can be done with the help of ‘Bus’ and ‘Adapter’ in the following way −

The concept of “bus”, which is achieved through a messaging server like JMS or AMQP, is used to decouple different applications from one another.

The concept of “adapter”, responsible for communicating with backend application and transforming data from application format to bus format, is used between applications and bus.

The data or message passing from one application to another through the bus is in a canonical format which means there would be one consistent message format.

The adapter can also perform other activities like security, monitoring, error handling and message routing management.


ESB’s Guiding Principles
We can call these principles as core integration principles. They are as follows −

Orchestration − Integration of two or more services to achieve synchronization between data and process.

Transformation − Transforming data from canonical format to application specific format.

Transportation − Handling protocol negotiation between formats like FTP, HTTP, JMS, etc.

Mediation − Providing multiple interfaces to support multiple versions of a service.

Non-functional consistency − Providing mechanism for managing transactions and security also.

Need of ESB
ESB architecture enables us to integrate different applications where each application can communicate through it. Following are some guidelines on when to use ESB −

Integrating two or more applications − Use of ESB architecture is beneficial when there is a need to integrate two or more services or applications.

Integration of more applications in future − Suppose if we want to add more services or applications in future, then it can be easily done with the help of ESB architecture.

Using multiple protocols − In case if we need to use multiple protocols like HTTP, FTP, JMS etc., ESB is the right option.

Message routing − We can use ESB in case if we require message routing based on message content and other similar parameters.

Composition and consumption − ESB can be used if we need to publish services for composition and consumption.



P2P integration vs. ESB integration
With the increase in number of applications, a big question in front of developers was how to connect different applications? The situation was handled by hand-coding a connection between various application. This is called point-to-point integration.

Rigidity is the most obvious drawback of point-to-point integration. The complexity increases with the increased number of connections and interfaces. The disadvantages of P-2-P integration leads us to ESB integration.

ESB is a more flexible approach to application integration. It encapsulates and exposes each application functionality as a set of discrete reusable capabilities. No application directly integrates with other, instead they integrate through an ESB 

For managing the integration, ESB has the following two components −

Service Registry − Mule ESB has Service Registry/Repository where all the services exposed into the ESB are published and registered. It acts as a point of discovery from where one can consume the services and capabilities of other applications.

Centralized Administration − As the name implies, it provides a view of transactional flows of performance of interactions occurring inside the ESB

ESB Functionality − VETRO abbreviation is generally used to summarize the functionality of ESB. It is as follows −

V(Validate) − As the name implies, it validates the schema validation. It requires a validating parser and up-to-date schema. One example is an XML document confirming to an up-to-date schema.

E(Enrich) − It adds additional data to a message. The purpose is to make message more meaningful and useful to a target service.

T(Transform) − It converts the data structure to a canonical format or from a canonical format. Examples are conversion of date/time, currency, etc.

R(Routing) − It will route the message and act as a gatekeeper of the endpoint of a service.

O(Operate) − The main job of this function is to invoke the target service or interacts with the target app. They run at the backend.

VETRO pattern provides overall flexibility to the integration and ensures that only consistent and validated data will be routed throughout the ESB.


What is Mule ESB?
Mule ESB is a lightweight and highly scalable Java-based enterprise service bus (ESB) and integration platform provided by MuleSoft. Mule ESB allows the developer to connect applications easily and quickly. Regardless of various technologies used by applications, Mule ESB enables easy integration of applications, enabling them to exchange data. Mule ESB has the following two editions −

Community Edition
Enterprise Edition
An advantage of Mule ESB is that we can easily upgrade from Mule ESB community to Mule ESB enterprise because both the editions are built on a common code base.

Following features are possessed by Mule ESB −

It has simple drag-and-drop graphical design.
Mule ESB is capable of visual data mapping and transformation.
User can get the facility of 100s of pre-built certified connectors.
Centralized monitoring and administration.
It provides robust enterprise security enforcement capabilities.
It provides the facility of API management.
There is secure Data Gateway for cloud/on-premise connectivity.
It provides the service registry where all the services exposed into the ESB are published and registered.
Users can have control through a web-based management console.
Rapid debugging can be performed using service flow analyzer.

The motivations behind the Mule project were −

to make things simpler for the programmers,

the need of lightweight and modular solution that could scale from an application-level messaging framework to an enterprise-wide highly distributable framework.

Mule ESB is designed as an event-driven as well as programmatic framework. It is event-driven because it is combined with unified representation of messages and can be expandable with pluggable modules. It is programmatic because programmers can easily implant some additional behaviors such as specific message processing or custom data transformation.

History
The historical perspective of Mule project is as follows −

SourceForge project
Universal Message Object (UMO) API was at the core of its architecture. The idea behind UMO API was to unify the logic while keeping them isolated from the underlying transports.


Version 1.0
It was released in April 2005 containing numerous transports. The key focus of many other versions followed by it, was on debugging and adding new features.

Version 2.0 (Adoption of Spring 2)
Spring 2 as configuration and wiring framework was adopted in Mule 2 but it proved to be a major over-haul because of the lack of expressiveness of the required XML configuration. This issue was resolved when XML Schema-based configuration has been introduced in Spring 2.

Building with Maven
The biggest improvement that simplified Mule usage, both at development and deployment times, was the use of Maven. From version 1.3, it started to be constructed with Maven.

MuleSource
In 2006, MuleSource got incorporated “to help support and enable the rapidly growing community using Mule in mission-critical enterprise applications”. It proved to be the key milestone for Mule Project.



Mule’s Core Concept
As discussed, Mule ESB is a lightweight and highly scalable Java-based enterprise service bus (ESB) and integration platform. Regardless of various technologies used by applications, Mule ESB enables easy integration of applications, enabling them to exchange data. In this section, we will discuss about Mule’s core concept coming into play to make such integration happen.

For this, we need to understand its architecture as well as building blocks.

Architecture
The architecture of Mule ESB has three layers namely, Transport layer, Integration layer and Application layer 


Generally, there are following three types of tasks that can be performed to configure and customize Mule deployment −

Service Component Development
This task involves development or re-using the existing POJOs, or Spring Beans. POJOs is a class with attributes that generates the get and set methods, cloud connectors. On the other hand, Spring Beans contains the business logic to enrich messages.

Service Orchestration
This task basically provides the service mediation that involves configuring the message processor, routers, transformers and filters.

Integration
The most important task of Mule ESB is the integration of various applications regardless of the protocols they are using. For this purpose, Mule provides transport methods that allow receiving and dispatching the messages on various protocol connectors. Mule supports many existing transport methods, or we may also use a custom transport method.

Building Blocks
Mule configuration has the following building blocks −


Spring beans
The main use of Spring beans is to construct service component. After constructing spring service component, we can define it through a configuration file or manually, in case you do not have configuration file.

Agents
It is basically a service created in Anypoint Studio before Mule Studio. An agent is created once you start a server and will be destroyed once you stop the server.

Connector
It is a software component configured with the parameters that are specific to protocols. It is mainly used for controlling the usage of a protocol. For example, a JMS connector is configured with a Connection and this connector will be shared among various entities in charge of actual communication.

Global Configuration
As the name implies, this building block is used to set the global properties and settings.

Global Endpoints
It can be used in Global Elements tab which can be used as many times in a flow −

Global Message Processor
As the name implies, it observes or modifies a message or message flow. Transformers and filters are the examples of Global Message Processor.

Transformers − The main job of a transformer is to convert data from one format to another. It can be defined globally and can be used in multiple flows.

Filters − It is the filter that will decide which Mule message should be processed. Filter basically specifies the conditions that must be met for a message to be processed and routed to a service.

Models
In contrast to Agents, it is a logical grouping of services which are created in studio. We have the liberty to start and stop all the services inside a specific model.

Services − Services are the one that wrap our business logic or components. It also configures Routers, Endpoints, transformers and filters specifically for that service.

Endpoints − It may be defined as an object on which services will inbound (receive) and outbound (send) messages. Services are connected through endpoints.

Flow
Message processor use flows to define a message flow between a source and a target.

Mule Message Structure
https://www.tutorialspoint.com/mulesoft/mulesoft_the_mule_project.htm

```