**Monolith to Microservice architecture**
```
software-architecture-breaking-a-monolith-into-microservices:
have a monolith application?
solution= microservice?
how do I start?
is there a process?
challenges?

Gather Goals:
Move everything to cloud with assumption infra cost is reduced
Do a redesign - it doesnot really matter as they don't have the compition in the market
Release native Apps for android and IOS - customer are happy with existing website not really a requirement from customers
Use kubernetes - there is no business value attached to it.
Scale better and more effectively under load-  yes we can scale horizontally very useful during high load
Reduce build times - helps increase developer productivity and effect and ofcourse the business
Release more often - new features can be released very frequently without disturbing other features. possiblity of breaking other existing code is less.
Reduce the blast radius of errors - errors are centralized and other features are not effected because of issue in one service
Become polyglot to attract specialists - new joiners can quickly understand the features in microservice architecture rather than understanding whole monolith at once


Focus on what matters:
Scaling on required features will help in reducing infra cost on other services that don't have more traffic
Functionality split into dedicated microservices - developers don't have to build everything but just their service
but when integration testing when everything is put together, there will be no gain
Integration testing becomes more complicated as a lot of moving parts need to be combined into a running application.
but this would be a good time to add proper automated integration tests
release fequency can be dealt with microservices, this is one main benefit they provide
with microservices we can develop the features in parallel and also rolled out independently
with microservices problems might get more complex, as now the network layer and plenty of small containers are added to it.
we can develop different services in different programming languages and then integrate them.





```
