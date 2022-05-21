**Java Memory Management**
```
Open Java Virtual VM
Eclipse Memory Analyser
Apache JMeter


How memory Works in java?
stack
heap

when applications run they need access our computer memory:
This memory is split into 2 sections
stack and heap
every thread will have its own stack
java knows when the data on the stack can be destroyed
we push data on the top of the stack with FIFO operation

public class Main{

public static void main(String... args){

int value=7;
value=calculate(value);
}

public static int calculate(int data){
int tempValue=data+3;
int newValue=tempValue*2;
return newValue;

}
}

stack:
newValue=20
tempValue=10
data=7
value=7
args=emptyarray


data on the stack can be accessed by the thead that own the stack
role of heap:
allows to store data that has longer life time than single block of code or function.
ex: objects need to be shared across the methods.
it is huge area for storing the data
stack is tied to a thread where as heap is used across the threads
In java All objects are stored on heap
stack is used for local primitive variables like int, double
for strings, Integer, customobjects heap is used.



for objects variables are created on stack and pointed to the object on the heap
in summary:
objects are stored on the heap
variables are a reference to the object
Local variables are stored on the stack


public static void main(String... args){

List<String> myList=new ArrayList<>();
myList.add("one");
myList.add("two");
myList.add("three");
printList(myList);
System.out.println(myList);

}

public static void printList(List<String> data){

String value=data.get(1);
data.add("four");
System.out.println(value);
}

stack:
data
myList


heap:
List[list(0)---> String("one")
list(1)---> String("two")
list(2)---> String("three")
]




Passing variables by value:
when a value is passed to a method a copy of the value is passed this is called pass by value

passing by reference is not possible

final keyword:
it is similar to constant keyword used in other languages
if we try to reassign we get compile time error


Escaping References:
Encapsulation binds data and methods of the class
it provides tight control on modification from outside
but in case of references when reference of an object is provided user can modified from outside of the class
it is like making the state of the class as public
causing the state being modified from outside
references can only be escaped if there are methods which can return references of the object.

public Map<String,Customer> getCustomers(){

	return this.records;
}

to be replaced as

public Map<String,Customer> getCustomers(){

return new HashMap<String,Customer>(this.records);

}

public Iterator<Customer> iterator(){

	return records.values().iterator();
}


Collections.unmodifyableMap
Collections.unmodifyableList

public Map<String,Customer> getCustomers(){

return Collections.unmodifyableMap(this.records);

}



in case of normal objects we need to keep readonly methods in interface and use it as return type of the actual object
so that as the interface don't have write methods it cannot access write methods of the objects
here one loop hole is reference can be type cased again to actual class object and can call write methods


Garbage Collection:
Stack is very efficient
Java can  manage it very easily.
It knows that when call is completed it can destroy the stack
java creates objects on heap
Strings are immutable
VM will place string literals in SCP

String one="hello";
String two="hello";

if(one == two){
System.out.println("they are same objects");
}else{
System.out.println("they are different objects");
}

String three=new Integer(76).toString();
String four="76";

if(three == four){
System.out.println("they are same objects");
}else{
System.out.println("they are same objects");
}


three=new Integer(76).toString().interim();
if(three == four){
System.out.println("they are same objects");
}else{
System.out.println("they are same objects");
}




intern method is used to place string object on SCP.

Garbage eligibility:
Java cleans objects automatically.
objects that are not freed continue to consume memory. this is a memory leak
Java avoids memory leaks by:
Running on a VM.
Adopts a Garbage Collection strategy
Any object on the heap which cannot be reached through a reference from stack is eligible for garbage collection

All unreachable/unreferenced objects are eligible for garbage collection
objects that are reference to each other causing circular references but no reference on stack are also eligible for garbage collection

garbage collection is automatic process

finalize method is called by garbage collector.

understanding what are soft leaks are:
a third party library can somehow keep the objects live.

maxheap property:
-Xmx10m
heap with 10MB
we will get out of memory error
GC overhead limit exceeded

JvisualVM



Generational GC:
Mark and sweep
GC will search for objects that need to be retained.
it is two state process:
1. marking: program execution is paused, this is called stop the world event. Marking cannot work properly if there are any thread still executing. so All the threads in the application are paused
Then GC will check the every single live reference, it simply looks every variable on the stack and follows its reference
the object that is found at the end of the reference is marked alive and it then follows any other references
that object has.
that objects that are not marked as alive are freedup.
object that are marked are moved to a contigous block of memory. 
this stop the heap from becoming fragmented.


2. Sweeping


In case of mark sweep collection, application is paused or frozen during Garbage collection time.
this is not acceptable. to avoid this we have generational garbage collection.
Most objects don't live for long
If an object survives it is likely to live forever

Stack
Heap: young and old generation
gc on young generation is faster. objects that survive for longer time are moved to older generation
gc of young generation is called minor collection
gc on older generation is called major collection

for heap dump analysis:
www.eclipse.org/mat
Memory Analyzer(MAT)


In java6 there are permgen
permGen is never garbage collected.
if permgen is full then application will crash.
there are two types of objects that go into permgen:
internalized strings: that is strings which are placed into a pool for reuse.
and everytime we create a class the metadata for that class is placed into permGen.
for each class that is present in application there is some information that is need to live in PermGen space.

We might have seen sometimes PermGen Space out of memory.
this error mean our application have too many classes or internalized strings.
this is not due to memory leaks or faults in the code.
The only thing you can to avoid PermGen error is to increase the sie of the PermGen within the heap
Each time we deploy the application on the server eventhough though most of the classes have no change a new complete set of metadata for all the classes will be created in PermGen.
all the previous deployment metadata of classes is still in the PermGen but will never be referred to.
As there is no Garbage collection on PermGen it will never get cleared out.
So as we do deployment multiple times on a same server PermGen will eventually run out of space.
For this reason on the live server you might want to consider stopping and restarting tomcat or whatever your service application is each time you deploy a new version of the code to avoid permgen becoming full.
This is how Heap worked in Java6 and earlier versions.
Heap: young, old, PermGen

From java7 internalised strings are no longer stored in PermGen.
This mean sinternalized strings are in the old part of the heap and can therefore be garbage collected.
if your application uses lot of strings then this won't be a contributing factor to PermGen crashes anymore.

In Java8 they removed the PermGen altogether.
instead they created something else called the MetaSpace.
which is where the metadata field classes are placed.
Metaspace is a separate area of memory and it's not part of the Heap.
Instead it is allocated outside of the computer's native memory so the maximum available space for the Metaspace is the total system memory for your computer.
we can also cap the max memory for the MetaSpace, if we don't do that then Virtual Machine will just grow the MetaSpace as it needs to.
Useful feature of the MetaSpace is that when classes are no longer creatable, the metadata related to those classes is then removed.
So if we are running tomcat under java8 then everytime we redeploy all the old class metadata in the metaspace will get removed and MetaSpace won't grow each time we redeploy.
So at the time of recording we think that this will remove the old PermGen style Problems on the server.
Although on the live server of Java8 we might want to keep an eye on how much memory your app is using over time.
It should be okay because java8 is not yet widely used on production servers as there could be some unidentified issues.


Tuning the Virtual Machine:





```

