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