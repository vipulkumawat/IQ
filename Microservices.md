**Microservices:**

Monolithic: architecture is a single piece, all components are interconnected and inter dependent or it is a tightly coupled software where each and every component should be present inorder to execute the code.

Challenges of Monolithic Architecture:
Modularity and understanding of code breaks down over a period of time.
It will be difficult to understand how to correctly implement the change.
Quality of code declines overtime.
It blocks Continuous Development
Unscalable
If one service goes down entire System will go down.
Inflexible meaning becomes really difficult to adopt a new framework,
it becomes barrier to adopt new technology.

what is Microservice Architecture?
It is an architectural style that structures an application as a collection of small autonomous services, modelled around a business domain. In simple terms it ia self contained process which avails different and unique business capabilities. Large application can be broken down to smaller multiple services which together acts as one large system. these microservices communicate through apis, major advantage of breaking down is each microservice can focus on one single business capability which leads to better quality and throughput. 

Microservices communicate with rest or messaging.
communication between microservices is a stateless communication each pair of request and response is independent transaction because of this microservices can communicate effortlessly.

Each microservice is responsible for its own datamodel and data because of which interaction with each microservice is handled by different instance unlike in monolithic architecture.
8:57
https://www.youtube.com/watch?v=gfWr2_H39N0
