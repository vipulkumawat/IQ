**AWS**

```
Cloud computing defined
benefits of cloud computing
cloud computing models
aws history
aws platform
aws products overview
aws security  and compliance
regions and availability


cloud example:
dropbox
google
microsoft azure
amazon web services



cloud computing is processing on the internet or a private network where the exact processor location is unknown

use of aws can reduce hardware, operational and deployment cost
cloud  computing still uses servers, they are simply hidden from the view


benefits of cloud computing:
reduces hardware cost
operational cost of managing servers
deployment cost is reduced in figuring out the right type  of servers
scale out or scale in easy with cloud

Increased resiliency by removing unhealthy servers and spinning up new server
Performance is increased as it can scale out when required as traffic increases by auto scaling
Pay as you use
Capacity can be increased as required as aws storage feature gives as needed



cloud computing models:
Full cloud or all in cloud in model:
db/application/general storage  everything on cloud

hybrid deployment:
some resources are internal, others are in the cloud. high performing systems on cloud and low performing systems on cloud.
archive storage, backups etc
-processing
-database
-application logic


IaaS: Infrastructure as service
-Entire infrastructure in cloud
-Platfoorms and software run on others infrastructure
-yoou must manage it all

PaaS: platform as a service
you don't manage the infrastructure
applications are deplooyed on platform


SaaS - Software as a Service:
-someone else develps the software
-You use it from the cloud

AWS Platform:
built on top of compute capability
storage
objects
block based storage
virtual  private cloud
AWS identity and access management(security)
database as a service
Amazon VPC



compute:
EC2
lightsail
ECS
EKS
Lambda
Batch
Elastic Beanstalk



with EC2 we need to manually setting up the instance and what kind of proocessor or in memory do you want to use, what OS you need to run and so forth

with Beanstalk we can ask I need a platform to run the application, and beanstalk takes care of what databases that app need, what instances needed, anything that application needed to run application



Storage:
S3
EFS
Glacier
Storage Gateway


S3 is object based, put things into buckets storage service

EFS: we need to see how it works in connection with EC2 instance.

Glacier: we keep the things that might not needed so often. It is used for archival purposes. we keep things that are not needed for us very often. it is least expensive storage we have in AWS. these files need not require superfast bandwidth.

storage gateway: to access storage that is in the cloud locally or locally that is in the cloud seamlessly, 


Databases:
RDS
Dynamodb
Elastic Cache
Neptune
Amazon Redshift


Migration:
AWS migration Hub
Application Discovery Service
Data Basee migration service
Server Migration Service
Snowball


snowball: when bunch of data to keep it in aws quickly we use this service.
it can be TBs of data also



Network and Content delivery
VPC
CloudFront
Route 53
API Gateway
Direct Connect




Management tools:
Cloud watch
AWS Autoscaling
Cloud formation
Cloud Trail
Config
...


MediaServices:
Elastic Transcoder
Kinesis Video Streams
Media Convert
Media Live
Media Package
Media Stoore
Media Tailor



Machine Learning:
...

Analytics:
Kinesis
...


Security, Identity and Compliance:
IAM
Cognito
Secrets Manager
GuardDuty
Inspector
...
AWS Organizations
Cloud HSM
Directory Service
WAF and Shield
...


AWS costmanagement:
AWS Cost explorer
AWS Budgets


Mobile Services:
Mobile Hub
AWS AppSync
Device Farm



Application Integration:
Step Functions
Amazon MQ
Simple Notification Service
Simple Queue Service
SWF


Customer Engaugement:
Amazon Connect
Pinpoint
Simple Email Service

Security Services include identity and Access management(IAM) and AWS organizations
Cost management services help you track the costs of your AWS solutions
The new IoT services will likely get an exam of their own in the future

Security is a shared responsibility
Customer Responsibility: Customer data, Client side data encryption and Data integrity Operation

AWS Responsibility:
Platform and Application management
Operating System and Network Configuration
AWS Foundation Services(Compute, Storage, Database, Network)
AWS Global Infrastructure (Region, Availability Zone, Edge Locations)

The AWS Customer is responsible for the security of their data and client side operations
AWS is responsible for the security of the services they offer
While AWS is responsible for the security of the cloud, you are responsible for the security in the cloud

Region: physical location or boundary with AWS data centers in that location.


Availability zone: it is 1-6 data centers, there is redudant power and networking across different data centers, 
so that if one data center fails the other data center continue in operation hence its available
Multiple availability zones are within a region

Regions(Availability Zones( datacenters))
This is the hierarchy of how AWS is deployed worldwide

aws.amazon.com/about-aws/global-infrastructure

Edge Area(Edge Location): are servers located near customers

Edge areas are used by cloud front, so when we want to cache web pages close the users, we can pick an edge area that you can use
and get it as close to those users as possible


An AWS region is a physical location or boundary containing AWS data centers
An AWS AvailabilityZone(AZ) is one or more data centers with redundant power and networking
Multiple AZs are within Regions

```

**aws-essential-training-for-architects**


```
Cloud concpets:
The term cloud generally refers to anything involving hosted services over the internet.
These hosted services are categorized as one of 
IaaS
PaaS
SaaS

c#3
Application Data
Database Data

C#2
Runtime
OS

C#1
Servers
Load balancers
File Storage
Networking

IaaS: C#1
PaaS: C#1+ C#2
SaaS: C#1+C#2+C#3


Cloud services provide flexibility for controlling costs than traditional on-premise hosting environments.
Cloud allows for minimum upfront investment in the infrastructure needed to launch an application.
Companies don't need to manage server, power supplies, routers and cables, all the parts and connections between them
that are needed to host the technology product.

Cloud offers Just-in-time infrastructure.
this allows to allocate exactly what is needed and only when it is needed.

No need to guess the capacity of resources to provision when launching new application.

No need to incurr the cost when getting it wrong.

Autoscaling is key beneift of cloud.
Resources can be scaled out by adding more resources, scaled in by removing resources.
scaled up by making resources bigger
scaled down by making resources smaller
to match demand without any human intervention

Cloud allows applications to react to changing load and demand in an automated fashion
we can also do proactive scaling in anticipation of an expected event

On-Demand scaling

High Availability and Disaster Recovery Benefits helps against local and regional area outages.
and hosts data in closest proximity to the users of your application
This helps in increasing speed and performance


Cloud elasticity:
refers to its ability to expand or contact.

Cloud provides scalable infrastructure means ability to expand and contract inorder to handle a growing or diminishing workload.
This is called scaling and this is why the term elastic is used to describe cloud services.


what resources are needed while designing application for cloud?




Failure Now ---> Failproof Later

Thinking about failure at the beginning of a project causes recovery strategies to be part of the design process,
which will then lend itself to a better, more stable end product.
Single point of Failure is Bad
One major rule of thum to consider when designing for failure is to strive to avoid single points of failure.

Elasticity refers to the ability of the cloud to scale resources to match the demand of your applications.

There are few methods typically to achieve this scaling.
-> scale components on a regular, fixed basis.
ex: hourly, daily or weekly
This might work if an application has highly predictable traffic patterns.
if traffic increases during business hours and slows down at night, this allows scaling of resources at specific time intervals to accomodate this pattern.

scale the components in anticipation of an expected event.
involves scaling out or up due to some known marketing campaign or event where sharp increase in demand are expected.

setup monitoring of certain metrics and scale in reaction to metrics raising above or falling below certain thresholds
ex: spikes in CPU utilization or network I/O
If these metrics breach certain thresholds, components can scale automatically and immediately either in or out.

This way system is coninuously matching supply with demand.

Regardless of method, in order to take full advantage of scaling:
 application deployment process need to be automated.
System configuration adjustment and application design  must also be adjusted to accommodate scaling.
AWS has deployment services
One of the keys to automating application processes is a concept referred to as bootstrapping.

Bootstrapping is a selfsustaining start-up process that can run on its own.
in AWS, its a process needed to get applications up and running on an EC2 instance
Cloud is called Elastic due to its ability to expand and contract resources to match the demand of the applications you build on the cloud.

you must design your applications in such a manner so that they are able to take advantage of this elastic nature of the cloud.
Decoupling or loose coupling refers to a design principle concerned with minimizing dependencies between components in order to improve scalability of applications.



Communication between webserver & Application servers:
with load balancer or Message Queue


Few AWS services to decouple application components:
Elasitc Load balancer
Simple Message Queue
Simple Notification Service
Simple workflow engine


Cloud Best practices: Optimize for performance
For performance optimization you are likely to be about decreasing latency and increasing throughput of the systems.
making systems go faster and do more.

Optimizing any system in this manner is important to the success of the application.
optimizing performance as it pertains to be ability to use cloud computing resources efficiently.
good to know all available services and how they might best fit into a system's architecture.

Cloud watch is used to monitor application metrics and send notification alarms when thersholds are breached.

These alarms trigger automated actions by integrating with other services, such as Amazon Simple Queue Service, Amazon Simple Notification Service, and AWS Lambda just to remember a few.


Keep thigs secure:

Cloud provider(AWS provider):
Physical security
Infrastructure
Equipment
Seperation from other customer





Amazon EC2 uses public key cryptography to encrypt and decrypt log information.
public key cryptography uses public key to encrypt a piece of data such as password and receipient uses private key to decrypt the data
public and private key together knows as key pair
key pair should be used to manage EC2 instances
you use public key for launching instance but uses private key for logging into the instance

linux based instances doesn't have passwords but this key-pair is used to log in using SSH.

for windows instances we use RDP for login and keypair is used to obtain administrative password

console can be used to create a new key pair.

Rotate the keys so often as it is a good security practice

pem file is the private key of the public-private key pair that we discussed

we use ssh to login to instance we need to have proper permissions on pem file.

AWS security groups are the virtual firewalls in the cloud that allow the control of inbound and outbound traffic on certain resources.
security groups determine who can communicate with the resources that below to that group.

Traffice rules can be setup once and can be applied to multiple resources

resources can be assigned to multiple security groups allows the flexibility to mix and match security groups with resources to accommodate differing security management needs.

if no security group is assigned default security group will be assigned by aws with defaulting to no access to the resource
security group controls inbound and outbound traffic to a resource.

These security rules composed of traffic type, an underlying protocol, a port or a port range, and a source

traffic type:
ssh
rdp
http

actually underlying protocol is fixed by the type choosen
ex: 
Http--underlying is->TCP,
 UDP, 

port range
source can be specified by IpAddress or security group




CIDR notation: Class less internet domain routing


Cloud Application Architecuture Security Tip:
use security groups to control the inbound and outbound traffic to AWS resources and follow the principle of least privilege when defining your rules


 

VPC: Amazon Virtual Private Cloud
enables AWS resources to be launched into a virtual network defined by customer


EC2 classic:
Runs in a single flat network
Network shared with other AWS customers
Automatically be associated with a public and private IP
Everything internet addressable
After December 4th,2013- no longer available


VPC:
Logically isolated to ony one AWS account
Not automatically addressable via the public internet
Private and public interface control
Both inbound and outbound traffic can be controlled
Multiple IP addresses can be assigned
Elastic interface networks can be assigned
VPN Connection
More flexibility is provided than EC2 classic

Default VPC:
No configuration
Read to use


VPC setup:
choose which region
Specify range of IP addresses for the entire VPC network
CIDR notation
Ensure range allows for growth
Create Subnets
Subset IP range of entire VPC network
Defined within Availability Zones and don't span between them

Gateway interfaces are attached

private Subnet
public Subnet has internet routed gateway
VPN only subnet




Setup custom VPCs to better protect AWS resources and fully control the security and topology of your network




















``