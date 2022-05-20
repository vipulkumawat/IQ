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








```

