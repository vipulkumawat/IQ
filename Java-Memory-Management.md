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











```

