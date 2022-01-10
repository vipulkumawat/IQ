


**Coforge:**
```
Scalability and Elasticity: 
Scalability is used to meet the static increase in the workload. Elasticity is used to meet dynamic changes, where the resources need can increase or decrease. Scalability is a long term planning and adopted just to deal with an expected increase in demand.
Computing
what is cloud native
What are broadcast variables and accumulators
what is class
what is jdk, jre, jvm
How do u clear cache in spark
what are packages in java
```

**MineralTree:**
```
What design patterns u used in application and how u implemented them in the project
explain microservice architecture
More on GCP cloud
Explain your project management
argocd, kuberneties
what is the ORM used in the project?
Different design patterns used in microservices
How your deployment process works?
```

**Reshamandi**
```
customer,productName,qty,pricePerQty
"Shiv,Apple,5,10",
"Shiv,Orange,1,5",
"Saurabh,Apple,2,10",
"Saurabh,WaterMelon,1,50",
"Adam,Orange,10,5",
"Ankur,Milk,2,15"


Using JavaStream do following:
Convert these strings to Java Objects with given header fields
Display all the data in decending order of the qty
complexity of the stream operations u are performing
Display HighestValue Products 
Display total value of the products
Write SpringBoot Application with above functionalities

I have a kafka topic with parition size 5, Lets say I have a lag of 72 million. What u can do to improve the consumption and clear the lag.
How hazelcast is different from redis
how hazelcast is different interms of distributed caching
In distributed system like redis and hazelcast how nodes are communicating?
What is difference between component, service, configuration, annotation in Spring
How do i exclude a class from being autoconfigured in spring boot application
difference between Conditional at Property and ConditionalOnClass
Difference between countdownlatch and cyclic barrier 
what is semaphore
Difference between embeddable collection and oneToMany Relationship in hibernate
How many ways u can implement oneToOne Relationship in hibernate
Explain More Components u worked On Kuberneties and GCP 
```



**Algonomy:**

```
Algonomy:
dsalgo: find min no of steps needed to reach end of the list
given a 2d array, can u use javastreams to print all elements of the 2d array.

what is ur approach to process million of records
If my worker thread need to return some thing what u will do
what is your worker thread ? it is runnable right, what is its return type? what is the return type of run method.

what are different designpatterns u haved used
what is builder design pattern
what are different ways that u can break ur singleton design pattern?
apart from deserialization and cloning process
during  serialization and deserialization how u can implement custom encryption and decryption

what are the new features of java8
what is predicate?
what are functional interfaces? ex: predicate, consumer,producer
what are the rules for writing functional interface? what is the structure of functional interface?
can u give some inbuilt functional interfaces
What is difference between ClassNotFoundException and NoClassDefFoundError
ClassNotFoundException is an exception while NoClassDefFoundError is an error. ClassNotFoundException occurs when classpath does not get updated with required JAR files while error occurs when the required class definition is not present at runtime
NoClassDefFoundError is an error that occurs when a particular class is present at compile time, but was missing at run time.

In springboot if I need to return both xml and json data what will u do?
If I need to handle my exceptions at single place what u need to do ?
are u aware of AOP? 

From UI if multiple users try to modify same data how u can avoid it?
what are different transaction states?







```

AJIO:
```
First Round : Technical + DSAlgo


```

**Snapdeal:**

```
Online Coding
FirstRound: DsAlgo

```

**Target:**
```
First Round: DS Algo
Second Round: Technical
Third Round: Thechnical
Fourth Round: Managerial Round

```

**Walmart:**
```
First Round: DSAlgo
Second Round: Technical Round
Third Round: Technical Round on Hazelcast
Fourth Round: Director Round

```

**Zeta:**
```
Find Illiterate villages that are a distance greater than d from given Literate village.
In an undefined matrix where navigation is only through diagonally find whether u can reach from Point A to Pont B and A->B->C.
```

**Paytm:**
```
Online Coding Round

```

**Visa:**
```
Online Coding Round
```

**Nike:**
```
Exploratory Call

```

**LatentView:**
```
DF1: userId, userName
DF2: userId, pageId, timestamp, eventType

def calculate(sparkSession: SparkSession): Unit = {
 val UserIdColName = "userId"
 val UserNameColName = "userName"
 val CountColName = "totalEventCount"

 val userRdd: DataFrame = readUserData(sparkSession)
 val userActivityRdd: DataFrame = readUserActivityData(sparkSession)


 val result = userRdd
   .repartition(col(UserIdColName))
   .join(userActivityRdd.repartition(col(UserIdColName))
   .select(col(UserNameColName))
   .collect(Collectors.Map(Function.identity,Collectors.counting));

 result.show()
}


```


**JohnDeere:**
```
Status codes:
https://developer.mozilla.org/en-US/docs/Web/HTTP/Status




```

**DeltaAirlines:**
```
how do u define the no of partitions for a topic?
why did u use kafka streams, why not other database for aggregations ?
are u using kafka internal rocks db or some external rocksdb?
talk about producer and consumer configurations u used in kafka?
within the topic how u will do parallel processing?
how do u control the speed of processing in kafka?
why do u need partitions?
what is the partition strategy, how do u decide how many consumers are required?
if ur consumer is suddenly down how do u ensure ur consumed message is processed successfully and how u have not lost any message either at producer or consumer end ?
how do u know or application or kafka knows when service is down the consumed message is not lost, how do u gaurantee it.
how ur application knows messages are produced successfully to kafka?
how do u ensure u are storing data successfully when application goes down suddenly?
I have two consumers, I want to consumer same message at two different consumer how u can do that?
when the consumer is down and comes back online how can I ensure my consumer is consuming the lag data. offset.reset set to earliest option
when happens when a kafka consumer goes down? does rebalancing and assings the partition to a different consumer.
If I need to maintain the order of events in kafka?
How do u ensure u are hazelcast is updated along with cassandra ?

39:50sec

```