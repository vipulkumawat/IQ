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

Spring Beans
Agents
Connector
Global Configuration
Global Endpoints
Global message Processor
Models
Flows

Global Message Processor:
Global Transformer
Global Filter

Models:
Services- Inbound, Outbound, Component

Flows: Source, Target

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

Mule Message consists of two main parts −

Header
It is nothing but the metadata of the message which is further represented by the following two properties −

Inbound Properties − These are the properties which are automatically set by the message source. They cannot be manipulated or set by the user. In nature, inbound properties are immutable.

Outbound Properties − These are the properties that contain metadata like an inbound property and can set during the course of flow. They can be set automatically by Mule or manually by a user. In nature, outbound properties are mutable.

Outbound properties become inbound properties when the message passes from the outbound endpoint of one flow to the inbound endpoint of a different flow via a transport.

Outbound properties remain outbound properties when the message is passed to a new flow via a flow-ref rather than a connector.

Payload
The actual business message carried by message object is called payload.

Variables
It may be defined as the user-defined metadata about a message. Basically, variables are temporary pieces of information about a message used by the application that is processing it. It is not meant to be passed along with the messages to its destination. They are of three types as given below −

Flow variables − These variables apply only to the flow in which they exist.

Session variables − These variables apply across all the flows within the same application.

Record variables − These variables apply only to records processed as part of a batch.

Attachments and Extra Payload
These are some extra metadata about message payload which is not necessarily appeared every time in message object.


MuleSoft - Mule in Our Machine:
Prerequisites
We need to satisfy the following prerequisites before installing Mule on our computer −

Java Development Kit (JDK)
Before installing MULE, verify that you have supported version of Java on your system. JDK 1.8.0 is recommended to successfully install Mule on your system.


Database
An application server or database is not required as the Mule Runtime runs as a standalone server. But if we need to access a data store or want to use an application server, following supported application servers or databases can be used −

Oracle 11g
Oracle 12c
MySQL 5.5+
IBM DB2 10
PostgreSQL 9
Derby 10
Microsoft SQL Server 2014

A Mule message, totally wrapped under Mule Message Object, is the data that passes through applications via Mule flows. The structure Mule’s message
Message Object
Message
Header(Inbound and Outbound property)
Payload
Attachment
Variable
Exception Payload

Windows Environments
set MULE_HOME
$MULE_HOME=C:\Downloads\mule-enterprise-standalone-4.1.5\

$MULE_HOME\bin\mule.bat
The above commands will run Mule in the foreground mode

Start Mule Services
We can start Mule as a Windows Service and as a Linux/Unix Daemon also.

Mule as a Windows Service
To run Mule as a Windows service, we need to follow the below steps −

Step 1 − First, install it with the help of following command −

$ $MULE_HOME\bin\mule.bat install




Deploy Mule Apps
We can deploy our Mule apps with the help of following steps −

Step 1 − First, start Mule.

Step 2 − Once Mule starts, we can deploy our Mule applications by moving our JAR package files to the apps directory in $MULE_HOME.

Stop Mule Services
We can use stop command to stop Mule. For example, the following example starts Mule as a Unix Daemon −

$ $MULE_HOME/bin/mule stop


We can also use remove command to remove the Mule Service or Daemon from our system. The following example removes Mule as a Unix Daemon −

$ $MULE_HOME/bin/mule remove





MuleSoft - Anypoint Studio:
MuleSoft’s Anypoint Studio is a user-friendly IDE (integration development environment) used for designing and testing Mule applications. It is an Eclipse-based IDE. We can easily drag Connectors from the Mule Palette. In other words, Anypoint Studio is an Eclipse based IDE for development of flow, etc.
Step 1 − First, click on the link https://www.mulesoft.com/lp/dl/studio and choose the Windows operating system from top-down list to download the studio.
Step 2 − Now, extract it into the ‘C:\’ root folder.

Step 3 − Open the extracted Anypoint Studio.

Step 4 − For accepting the default workspace, click OK. You will get a welcome message when it loads for the first time.

Step 5 − Now, click on Get Started button to use Anypoint Studio

Features of Anypoint Studio
Following are some features of Anypoint studio enhancing the productivity while building Mule applications −

It provides an instant run of Mule application inside a local runtime.

Anypoint studio gives us visual editor for configuring API definition files and Mule domains.

It has embedded unit testing framework enhancing the productivity.

Anypoint studio provides us the Built-in support to deploy to CloudHub.

It has the facility to integrate with Exchange for importing templates, examples, definitions and other resources from other Anypoint Platform organization.


Anypoint Studio editors help us design our applications, APIs, properties and configuration files. Along with designing, it also helps us to edit them. We have the Mule configuration file editor for this purpose. To open this editor, double-click on the application XML file in /src/main/mule.

To work with our application, we have the following three tabs under Mule Configuration file editor.

The Message Flow tab
This tab gives a visual representation of work flow. It basically contains a canvas that helps us check our flows visually. If you want to add Event Processors from the Mule Palette into the canvas, then just drag and drop and it will reflect in the canvas.


By clicking on an Event Processor, you can get the Mule Properties View with the attributes for the selected processor. We can also edit them.

The Global Elements tab
This tab contains the global Mule configuration elements for the modules. Under this tab we can create, edit or delete configuration files.

The Configuration XML tab
As the name implies, it contains the XML that defines your Mule application. All the changes you do here will reflect in the canvas as well as the properties view of event processor under the Message Flow tab.

Views
For the active editor, Anypoint studio gives us the graphical representation of our project metadata, properties with the help of views. A user can move, close as well as add views in the Mule project. Following are some default views in Anypoint studio −

Package Explorer
The main task of Package Explorer view is to display the project folders and files consisted in a Mule project. We can expand or contract the Mule project folder by clicking on the arrow next to it. A folder or file can be opened by double clicking it.


Mule Palette
Mule Palette view shows the event processors like scopes, filters, and flow control routers along with modules and their related operations. The main tasks of Mule Palette view are as follows −

This view helps us to manage the modules and connectors in our project.
We can also add new elements from Exchange.


Mule Properties
As the name implies, it allows us to edit the properties of the module currently selected in our canvas. Mule Properties view includes the following −

DataSense Explorer that supplies real-time information about the data structure of our payload.

Inbound and outbound properties, if available or variables.



Console
Whenever we create or run the Mule application, embedded Mule server displays a list of events and problems, if any, reported by Studio. Console view contains the console of that embedded Mule server.

Problems View
We can encounter many issues while working on our Mule Project. All those issues are displayed in the Problems view.



Perspectives
In Anypoint Studio, it is a collection of views and editors in a specified arrangement. There are two kinds of perspectives in Anypoint Studio −

Mule Design Perspective − It is the default perspective we get in Studio.

Mule Debug Perspective − Another perspective supplied by Anypoint Studio is Mule Debug Perspective.

On the other hand, we can also create our own perspective and can add or remove any of the default views.



Creating a Simple Http listener:
https://www.tutorialspoint.com/mulesoft/mulesoft_creating_first_mule_application.htm


DataWeave is basically a MuleSoft expression language. It is mainly used for accessing and transforming the data received through a Mule application. Mule runtime is responsible for running the script and expressions in our Mule application, DataWeave is strongly integrated with Mule runtime.


 data received through a Mule application. Mule runtime is responsible for running the script and expressions in our Mule application, DataWeave is strongly integrated with Mule runtime.

Features of DataWeave Language
Following are some important features of DataWeave language −

Data can be transformed from one format to another very easily.


For example, we can transform application/json to application/xml. The input payload is as follows −

{
   "title": "MuleSoft",
   "author": " tutorialspoint.com ",
   "year": 2019
}
Following is the code in DataWeave for transform −

%dw 2.0
output application/xml
---
{
   order: {
      'type': 'Tutorial', 
      'title': payload.title, 
      'author': upper(payload.author), 
      'year': payload.year
   }
}
Next, the output payload is as follows −

<?xml version = '1.0' encoding = 'UTF-8'?>
<order>
   <type>Tutorial</type>
   <title>MuleSoft</title>
   <author>tutorialspoint.com</author>
   <year>2019</year>
</order>
The transform component can be used for creating scripts that performs both simple as well as complex data transformations.

We can access and use core DataWeave functions on parts of the Mule event that we need as most of the Mule message processors support DataWeave expressions.


Prerequisites
We need to satisfy the following prerequisites before using DataWeave scripts on our computer −

Anypoint Studio 7 is required to use Dataweave scripts.

After installing Anypoint Studio, we need to set up a project with a Transform Message component in order to use DataWeave scripts.


https://www.tutorialspoint.com/mulesoft/mulesoft_dataweave_language.htm

https://www.tutorialspoint.com/mulesoft/mulesoft_message_processor_and_script_components.htm




```