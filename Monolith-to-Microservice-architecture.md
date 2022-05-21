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


Splitting capabilities into services:
Problems with Tight coupling and Anemic Services
-> Too much abstraction leads to anemic services
-> To avoid redundant code services need to call each other
-> Dependencies back to the monolith
-> Multiple services need to access the same data
-> Central data access services which ties these services together even more
-> shared code creates the same dependencies that were present on the monolith
-> The controller has to know many REST endpoints to accomplish anything



Solution: 
create separate services for each capability
Design and Migrate around capabilities

Best practices:
->Design your service around capabilities and not around single functions
->Make it a mantra that each service should be developed and deployed individually
->Make evolutionary, atomic iterations and use the proxy patterns to delegate functions to respective service calls


Refactor or Rewrite?
why Rewrite?
Splitting up monoliths is about capabilities and not code
Much of the code is specific to the monolith and won't be usable
you miss the oppurtunity to improve code
you miss the oppurtunity to use the right tool for the job
it's rarely faster than starting from scratch
exception: complex orthogonal calculations and logic


selection criteria:
Start with an orthogonal, edge service
Small and not too business critical
limited and simple functionality that can be developed fast

Review the architecture

Zero downtime migration





```
