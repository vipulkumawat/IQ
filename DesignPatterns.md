**Design Patterns**

_Pattern:_ Helps to identify the recurring problems and provides a pre-built solution that can be applied at its best in solving those problems.


All Convertor(Date util, Time Util, String Util) and Validation classes can be singleton.

GOF Pattern Catalog:

_Creational:_ It provides guidelines to instantiate a single or group of objects so called creational
* Abstract Factory
* Builder
* Factory Method
* Prototype
* Singleton

_Structural:_ It provides a manner to define relationship between classes
* Adapter
* Bridge
* Composite
* Decorator
* Facade
* Flyweight
* Proxy

_Behavioral:_ It defines communication between classes and objects
* Chain Of Responsibility
* Command
* Interpreter
* Iterator
* Mediator
* Memento
* Observer
* State
* Strategy
* Template Method
* Visitor

_Presentation Tier:_ This tier contains all the presentation tier logic required to service the clients that access the system
* Intercepting Filter
* Front Controller
* Application Controller
* View Helper
* Composite View
* Service to Worker
* Dispatcher View

_Business Tier:_ This tier provides business service required by the application clients
* Business Delegate
* Service Locator
* Session Facade
* Application Service
* Business Object
* Composite Entity
* Transfer Object
* Transfer Object Assembler
* Value List Handler

_Integration Tier:_ This tier is responsible for communicating with external resources and systems such as data stores etc.
* Data Access Object
* Service Activator
* Domain Store
* Web Service Broker

Explanation:
Singleton: If a class is singleton, an application allows only one instance of the class. Generally we create a class as singleton when we want global point of access to that instance.

How to make class singleton:
* Declare constructor of the class private(Other classes cannot create the object of the class directly)
* Declare a static method which can check and return only one object of the class(If method is non-static, to call it we need object of the class). As this method contains logic for creating the object, this method is called factory Method(static factory method)
* Declare a static member of same class type in the class. This member is used in above static method so that it tracks whether an object for the class is already exists, that's where u create first object u will assign it to a member variable. So, in the next call to the method, u just return the same object which u stored in the member variable.

 
public class DateUtil{
 private static DateUtil instance;
 private DateUtil(){}
 public static DateUtil getInstance(){
 if(instance==null){
 instance=new DateUtil();
 }
 return instance;
 }
 }


Eager Initialization: We can instantiate the instance eagerly before when class is loaded into memory 

public class DateUtil{
 private static DateUtil instance= new DateUtil();
 private DateUtil(){}
 public static DateUtil getInstance(){
 return instance;
 }
 }

Lazy Initialization:
In Most cases it is recommended to delay initialization process until the object is needed, but the problem with this is in a multithreaded environment when more than one thread are executing at the same time, it might end up in creating more than one instance of the class. To avoid this we use synchronized.

public static synchronized DateUtil getInstance(){

if(instance==null){
instance=new DateUtil();
}
return instance;


Instead of making the whole method as synchronized, it is enough to enclose only the conditional check in synchronized block.

public static DateUtil getInstance(){
synchronized(Dateutil.class){
if(instance==null){
instance=new DateUtil();
}
}
return instance;
}


Again we have a problem with the above piece of code, after first call to the getInstance(), in next calls to the method will check for instance ==null,
while doing so it acquires the lock to verify the condition which is not required. Acquiring and releasing the locks are costly, we need to avoid them as much we can. To fix this we can have a double level check for the condition as shown below:

public static DateUtil getInstance(){
if(instance==null){
  synchronized(DateUtil.class){
   if(instance==null){
   instance=new DateUtil();
}
}
}
return instance;
}


It is recommended to declare static member instance as volatile to avoid problem in a multi-threaded environment.

It seems above are best possible ways of creating a singleton class. Do u still see any drawbacks with above piece of code? yes, when we serialize and de-serialize a singleton class, the de-serialization process will creates as many no of objects for the singleton class which avoids the rule of singleton.

public static void main(String... args){
DateUtil du1=DateUtil.getInstance();
ObjectOutputStream oos=new ObjectOutputStream(new FileOutputStream(new File("D:\\DateUtil.ser")));
oos.writeObject(du1);
ObjectInputStream ois=new ObjectInputStream(new FileInputStream(new File("D:\\Dateutil.ser"))):
DateUtil du2=(DateUtil)ois.readObject();
System.out.println(du1==du2); //false

}

How to avoid creating more than one objects of singleton class even we serialize or de-serialize also, that's where we need to write readResolve() method as part of the singleton class. Deserailzation process will call readResolve method on the class to read the bytestream to build the object. If we write this method and can return the same instance of the class, we can avoid creating more than one object even in case of serialization as well.

Here is the complete code:

public class DateUtil implements Serializable{
private static volatile Dateutil instance;
private DateUtil(){}
public static DateUtil getInstance(){

if(instance==null){
synchronized(DateUtil.class){
if(instance==null){ instance=new DateUtil();}
}

}
return instance;
}
protected Object readResolve(){
   return instance;
}
}

Override clone method and throw CloneNotSupported Exception:
In order to not allow singleton class to be clonable from created objects, it is even recommended to implement your class from cloneable interface and override the clone() method. Inside the method throw CloneNotSupportedException to avoid cloning of the object.
clone() method is protected method in object class, which cannot be visible outside the class unless we override. That is why we need to implement Cloneable interface.

So the final Singleton class is below:

public class DateUtil implements Serializable, Cloneable{

private static volatile Dateutil intance;

public static DateUtil getInstance(){

if(instance==null{synchronized(DateUtil.class){ if(instance==null){instance=new DateUtil();}}}

return instance;
}
protected  Object readResolve(){ return instance;}
@Override
protected Object clone()throws CloneNotSupportedException{ throw new CloneNotSupportedException();}
}

When to use Singleton:
When a class has absolutely zero state. The methods of the class are not using any of the state of the class, rather the outcome of execution of the method depends on the parameter values with which u called the method. In such case you can declare the class singleton.
When a class has some state and it has some methods, methods are using the state and the state is readonly. So the outcome of the method doesn't depend on the state of the class rather would depend on the values with which u called the method. Such classes we can make them as singleton.
When a class has some state and methods, state is not read only but it is sharable state, means every other class in the application should see the same state of the object. In such case we don't need to create multiple objects, rather one instance of the class can be shared across multiple classes in the application.  Here the state the class is holding is a common state, we need to synchronize the read and write access to the class by making the methods of the class as synchronized to avoid concurrency issues.


Factory:( Creates objects of different family)
Not all objects in the java can be created out of new operator. few objects may be created by new, few have to be created by calling static factory(singleton) and other by passing other object as reference while creating etc.

main advantage of factory pattern is it abstracts the creation process of the class. ex: JDBC, connection is an interface in jdbc api, respective vendor drivers will implement the connection interface. So, jdbc has provided an factory class called DriverManager with method getConnection(); Every factory class has a method, it contains the logic for creating the object of another class, so it is called factory method.

FactoryMethod: Used for creating the object for family of related classes with in the hierarchy.(Creates objects of same family).

AbstractFactory: Creates objects of another factory(Factory of Factories) It is a super factory. Using factory design pattern we abstract the creation process of another  class. Using the abstract factory pattern we abstract the creation of family of classes.

Diff between abstract factory and Factory Method:
Abstract factory pattern delegates the responsibility of object instantiation to another object via comosition
Factory method uses inheritance and relies on subclasses to handle the desired object instantiation.

Template Method: it is behavioral design pattern,  in this we have a base template method, it defines an algorithm with some abstract steps. These steps have to be implemented by subclasses.

ex: 

public abstract class DataRenderer{
//algorithm is fixed, but to make algo work subclasses need to implement readData and processData.
public void render(){
String data=null;
String pdata=null;
data=readData();
pdata=processData(data);
System.out.println(pdata);
}

public abstract String readData();
public abstract String processData(String data);
}

XMLDataRenderer will implement readData and processData differently from TextDataRenderer.