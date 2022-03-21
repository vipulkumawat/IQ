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


Algonomy round1:
Single Linked list methods implementation: push,delete,traverse
write program to Find Minimum depth of the binary tree
In java how you can handle mutual exclusion scenario? means it should not be shared across multiple threads, if there is critical sections should not be shared across multiple threads? 
we can use synchronized. what does it happen really in the background with synchronized?
difference between wait and sleep method?
https://www.geeksforgeeks.org/difference-between-wait-and-sleep-in-java/
what is predicate in java?
what is supplier and how it is different from predicate? what are its usecases?
https://www.geeksforgeeks.org/supplier-interface-in-java-with-examples/
what are the design patterns you have used?
what is use of builder design pattern?
to provide a flexible solution to various object creation problems in object-oriented programming. The intent of the Builder design pattern is to separate the construction of a complex object from its representation.
If you don't want to seralize a variable then what you can use? if I want to do encrypt/decrypt during seralization and deseralization, what we can do?
In spring boot if I need to use central exception handling what we can do?
what are checked and unchecked exceptions?
class not found and no class defination error ?
https://dzone.com/articles/java-classnotfoundexception-vs-noclassdeffounderro#:~:text=ClassNotFoundException%20is%20an%20exception%20that,was%20missing%20at%20run%20time.






round2:
tell me how is your day to day life
where you stand in your team
give me one problem statement which you solved or in your career you have collabaratively solved the problem
explain what is the problem and how you solved it
when we have autoscaling how logs are captured?
keeping logging as different microservice..have you ever used it?
is central log microservice which can capture all logs, microservice focus on business logic and not worried about the logging queue.
do you see any problem with central logging microservice 
explain how log4j or slf4j works internally? why there is a need for separate framework, how you are getting benefitted from it and how it works?
can you explain how your sprint works, bascially what you do in the sprint ?

public class Algonomy {
    private static int number;
    private static boolean ready;
    private static class Tester extends Thread {
        @Override
        public void run() {
            while (!ready) {
                Thread.yield();
            }
            System.out.println(number);
        }
    }

    public static void main(String[] args) {
        List<Integer> list = new ArrayList<Integer>();
        list.add(4);
        list.add(2);
        list.add(1);
        list.add(0);
        list.add(3);
       list.remove(Integer.parseInt("4"));  
        System.out.println(list);

        new Tester().start();
        //number = 2;
        number = 4001;
        ready = true;

    }
}
O/p: what is the output?
// will output changes if we run it 10k times...we will get 4001 always or different output?


String exp= "((1+2)*(8-6))+4";
//solve the expression and give result with java code without using stacks
https://www.geeksforgeeks.org/stack-set-4-evaluation-postfix-expression/
https://www.tutorialcup.com/interview/stack/expression-evaluation.htm

what services you have used in AWS?
what sort of queries you have used in elastic search?
what is the max amount of data you have worked on and how much time it took to consume it in your microservice?

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
Two Arrays of Size n and m with distinct elements with non repeated element, find all possible pairs from numbers from both arrays, whose sum is x.
arr1[]={8,7,3,11,6} arr2={12,6,5,7,9,13} x=14, so possible pairs={8,6} {7,7}

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
What is the cache update strategy you are using in your application?
Until it is updated to cache we are having inconsitency with hazelcast, how u can handle it?
How do u maintain a distributed transaction across microservices ?
what is a transaction?
How do u ensure a transaction is successful?
How do u do internal communication between microservices?
using feign client in communication is synchrous, how can u do asynchronous communication between different microservices?
If any of the service is down or causing a delay and causing cascading failures in microservices, how u can avoid this cascading failure?
```
**StockX:**
``` 
what are disadvantages of microservices
if there is a change of data in database, how will microservices know the change
if second microservice is down how you will handle request the request coming via first microservice
how much tps your application is handling
how you are handling autoscaling in your application 
if there is sudden increase of traffic and if your pod takes some time to spinup how you will handle the scenario
why do you choose cassandra in your application not rdbms
what are different criteria's to consider for designing microservice
What is idempotence and which http headers are idempotent
If a customer tries to place an order twice through post api... How u  can avoid it

round1: cache implemenation
LFU Cache implemenation

round2: system design
At StockX, we have a catalog of products. On any of these products, you can place a bid (which indicates
that you’re willing to buy at a certain price) or an ask (which indicates that you’re willing to sell at a certain
price). Let’s imagine that we somehow didn’t have the endpoint that allows you to place bids. I’d like you
to design that for me.

1. Bidding – at what price a buyer is willing to pay
2. Selling- at what price a seller is ready to sell


round3:
Cultural fitness round

```


**Paypal:**
```
https://leetcode.com/discuss/interview-question/1194238/paypal-max-tasks-that-can-be-completed-in-given-budget
https://leetcode.com/discuss/interview-question/1331054/paypal-oa-se-ii-se-iii

https://www.hackerearth.com/problem/algorithm/beautiful-numbers-05de0f51-101121ca/
sol:
public class TestClass {

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        PrintWriter wr = new PrintWriter(System.out);
        int T = Integer.parseInt(br.readLine().trim());
                long[] preProcessArray = preProcess();
        for(int t_i = 0; t_i < T; t_i++)
        {
            String[] str = br.readLine().split(" ");
            int l = Integer.parseInt(str[0]);
            int r = Integer.parseInt(str[1]);
            wr.write(preProcessArray[r]-preProcessArray[l-1]+"\n");
            
         }

         wr.close();
         br.close();
    }

    static boolean check(int u) {
        int cnt = 40;
        while (cnt > 0 && u!=4) {
            int ans = 0;
            while (u > 0) {
                ans += (u%10)*(u%10);
                u /= 10;
            }
            u = ans;
            cnt--;
            if (u==1) {return true;}
        }
        return false;
    }

    static long[] preProcess() {
        long[] preProcessArray = new long[1000005];
        for (int i=1;i<=1000000;i++) {
            if (check(i)) {
                preProcessArray[i] = i;
            }
        }

        for (int i=1;i<=1000000;i++) {
            preProcessArray[i] += preProcessArray[i-1];
        }
        return preProcessArray;
    }
}


https://leetcode.com/discuss/interview-question/1194238/paypal-max-tasks-that-can-be-completed-in-given-budget
static int solve(int n, int t, int[][] task){
   PriorityQueue<Integer> pQueue= new PriorityQueue<>(Collections.reverseOrder());
   Arrays.sort(task,Comparator.comparingInt(o->o[0]));
   int pQueueSum=0;
   int max=0;
   for(int i=0;i<n;i++){
       int totalTime =t;
       int distance = 2*task[i][0];
       int remainingTime=totalTime-distance;
       int currEffort=task[i][1];
       if(remainingTime<0){
           break;
       }
       while(pQueueSum>remainingTime){
           pQueueSum-=pQueue.poll();
       }
       if(pQueue.isEmpty()&&remainingTime>currEffort){
         pQueue.add(currEffort);
         pQueueSum+=currEffort;  
       }
       else if(pQueueSum+currEffort<=remainingTime){
           pQueue.add(currEffort);
           pQueueSum+=currEffort;
       }
       else{
           Integer currMax=pQueue.peek();
           if(currMax != null && currMax>currEffort){
               pQueue.poll();
               pQueue.add(currEffort);
               pQueueSum=pQueueSum-currMax+currEffort;
           }
       }
       max=Math.max(max,pQueue.size());
   }
return max;
}


Paypal
Q1:
given a mapping={"0","1","abc","def","ghi","jkl","mno","pqrs","tuv","wxyz"}

number=23
result: ad, ae,af, bd,be,bf,cd,ce,cf

number=1
result=1
number=21
result= a1,b1,c1

number = 8909
result=tw0w,tw0x,tw0y,tw0z,tx0w,...

Q2: we have browserhistory and size of results you need to return.
LRU cache implementation

https://www.geeksforgeeks.org/combinations-strings-can-used-dial-given-phone-number/


```

**Cleartrip:**
```
Q1:https://leetcode.com/problems/car-pooling/
Q2: if there are events with below data:
User_id, timestamp, score
U1        12:00    2
U2        13:00    3
U1        13:02    2
U3        14:03    4

If you are provided dynamically a duration like past 30 minutes or past 1 hr. Can you tell me how you will get the score for that past duration

```

**ServiceNow:**
```
Round1:
Top View Of the tree
print possible words from string -    hellojavaworld
Find Kth Max element of the in the list of elements
Define cap theorum and explain with examples

round2: 
rotate matrix elements by  90 degrees
design inventory management system


```

**Cargill:**
```
round1
what are ER diagrams, class diagrams, sequence diagrams
Library management system system design
how do you decide which database to use?
what are different design patterns you have used?

Round2
Questions on spring boot and rest apis

Round3
Question on what challenges you faced and techstack related questions... More on current project architecture


```
**Oracle:**
```
```
**HPE:**
```

```

**SalesForce:**
```

round1:

 2. Fix the code issue with Roman to Integer conversion
3. Exception handling code output
 4. Foo bar program output
5. what is the best way to find length of last word in the given string
 public static void main(String[] args) {
        int a,b,c,d,f,g,x;
        x=1;
        a=b=c=d=f=g=0;
        try{
            try{
                switch (x){
                    case 1:
                        throw new Ex1();

                    case 2:
                        throw new Ex2();

                    case 3:
                        throw new Ex3();
                }
                a++;
            }catch (Ex2 ex){
                b++;
            }finally {
                c++;
            }
        }catch(Ex1 ex){
            d++;
        }catch(Exception e){
            f++;
        }finally {
            g++;
        }
        System.out.println(a+","+b+","+c+","+d+","+f+","+g);
    }
what is the output of above code ?
 interface iFoo{
    void func();
}

class Foo implements iFoo{
    public void func(){
        System.out.println("Foo");
    }
}
class Bar extends Foo implements iFoo{
    public void func(){
        System.out.println("Bar");
    }

    public void bfunc(){
        System.out.println("barFunc");
    }

public static void main(String... args){
    Foo f=new Foo();
        f.func();//

        iFoo i=f;
        i.func();//

        Bar b=new Bar();
        b.func();//

        ((Foo)b).func();//
        ((Foo)b).bfunc();//
        f=b;
        f.func();//

        i.func();//
}
}


round2:
 Q1.
public class Test implements Runnable{


public void run(){
sysout("test");
}

public static void main(String... args){

Thread t1=new Thread(new Test());
t1.start();
t1.start();
sopln(t1.getState());

}
}

Q2.
class MyThread extends Thread{

	public void run(){
		s.o.pln("run");
	}

	public void start(){
		s.o.pln("start");
	}
}

class Test{

	psvm(String... args){
	s.o.pln("mainStarted");
	MyThread t1=new MyThread();
	t1.start();
	s.o.pln("main has ended");
	}
}

Q3.
if there is a transaction to be happened
(a,b,10)
(b,a,20)
what are the issues that needs to be taken care and can you write some sudo code
 Q4.
write query to find duplicate records
Q5.
delete duplicate records from table
 Q6.

static int getCount(){

static int i=0;
return ++i;
}
any issue with the code

```

**Epsilon:**
```
```
**Paytm:**
```
```

**Amazon:**
```
```
**Cisco:**
```
```
**HCL:**
```
```

**MorganStanly:**
```
```

**Helodoc:**
```
```

**rightpoint:**
```
```

**delivery:**
```
```

**cropin:**
```
```

**amadeus:**
```
```

**expressb:**
```
```

**benz:**
```
```

**tekion:**
```
```

**gupshup:**
```
```

**Koch:**
```
```

**zscalar:**
```
```

**whatfix:**
```
```

**blueyonder:**
```
```

**deserve:**
```
```

**wipro:**
```
```

**omunius:**
```
```

**zynga games:**
```
```

**quizzizz:**
```
```
**Devon:**
```
```
**vmware:**
```
```
**Koreai:**
```
```
**byjus:**
```
```
**banyan data services:**
```
```
**Decimal Technology:**
```
```
