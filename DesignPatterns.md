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

``` 
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
```

Eager Initialization: We can instantiate the instance eagerly before when class is loaded into memory 
```
public class DateUtil{
 private static DateUtil instance= new DateUtil();
 private DateUtil(){}
 public static DateUtil getInstance(){
 return instance;
 }
 }
```
Lazy Initialization:
In Most cases it is recommended to delay initialization process until the object is needed, but the problem with this is in a multithreaded environment when more than one thread are executing at the same time, it might end up in creating more than one instance of the class. To avoid this we use synchronized.
```
public static synchronized DateUtil getInstance(){

if(instance==null){
instance=new DateUtil();
}
return instance;
}
```

Instead of making the whole method as synchronized, it is enough to enclose only the conditional check in synchronized block.
```
public static DateUtil getInstance(){
synchronized(Dateutil.class){
if(instance==null){
instance=new DateUtil();
}
}
return instance;
}
```

Again we have a problem with the above piece of code, after first call to the getInstance(), in next calls to the method will check for instance ==null,
while doing so it acquires the lock to verify the condition which is not required. Acquiring and releasing the locks are costly, we need to avoid them as much we can. To fix this we can have a double level check for the condition as shown below:
```
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
```

It is recommended to declare static member instance as volatile to avoid problem in a multi-threaded environment.

It seems above are best possible ways of creating a singleton class. Do u still see any drawbacks with above piece of code? yes, when we serialize and de-serialize a singleton class, the de-serialization process will creates as many no of objects for the singleton class which avoids the rule of singleton.
```
public static void main(String... args){
DateUtil du1=DateUtil.getInstance();
ObjectOutputStream oos=new ObjectOutputStream(new FileOutputStream(new File("D:\\DateUtil.ser")));
oos.writeObject(du1);
ObjectInputStream ois=new ObjectInputStream(new FileInputStream(new File("D:\\Dateutil.ser"))):
DateUtil du2=(DateUtil)ois.readObject();
System.out.println(du1==du2); //false

}
```
How to avoid creating more than one objects of singleton class even we serialize or de-serialize also, that's where we need to write readResolve() method as part of the singleton class. Deserailzation process will call readResolve method on the class to read the bytestream to build the object. If we write this method and can return the same instance of the class, we can avoid creating more than one object even in case of serialization as well.

Here is the complete code:
```
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
```
Override clone method and throw CloneNotSupported Exception:
In order to not allow singleton class to be clonable from created objects, it is even recommended to implement your class from cloneable interface and override the clone() method. Inside the method throw CloneNotSupportedException to avoid cloning of the object.
clone() method is protected method in object class, which cannot be visible outside the class unless we override. That is why we need to implement Cloneable interface.

So the final Singleton class is below:
```
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
```
When to use Singleton:
When a class has absolutely zero state. The methods of the class are not using any of the state of the class, rather the outcome of execution of the method depends on the parameter values with which u called the method. In such case you can declare the class singleton.
When a class has some state and it has some methods, methods are using the state and the state is readonly. So the outcome of the method doesn't depend on the state of the class rather would depend on the values with which u called the method. Such classes we can make them as singleton.
When a class has some state and methods, state is not read only but it is sharable state, means every other class in the application should see the same state of the object. In such case we don't need to create multiple objects, rather one instance of the class can be shared across multiple classes in the application.  Here the state the class is holding is a common state, we need to synchronize the read and write access to the class by making the methods of the class as synchronized to avoid concurrency issues.

**what are various concepts which can break singleton property of a class and how to avoid them:**
There are mainly 3 concepts which can break singleton property of a class

```
Reflection: Reflection can be caused to destroy singleton property of singleton class, as shown in following example:
 public static void main(String[] args)
    {
        Singleton instance1 = Singleton.instance;
        Singleton instance2 = null;
        try
        {
            Constructor[] constructors = 
                    Singleton.class.getDeclaredConstructors();
            for (Constructor constructor : constructors) 
            {
                // Below code will destroy the singleton pattern
                constructor.setAccessible(true);
                instance2 = (Singleton) constructor.newInstance();
                break;
            }
        } 
        catch (Exception e) 
        {
            e.printStackTrace();
        }     
    System.out.println("instance1.hashCode():- " 
                                      + instance1.hashCode());
    System.out.println("instance2.hashCode():- " 
                                      + instance2.hashCode());
    }

```
After running this class, you will see that hashCodes are different that means, 2 objects of same class are created and singleton pattern has been destroyed.

Overcome reflection issue: To overcome issue raised by reflection, enums are used because java ensures internally that enum value is instantiated only once. Since java Enums are globally accessible, they can be used for singletons. Its only drawback is that it is not flexible i.e it does not allow lazy initialization.

//Java program for Enum type singleton
public enum Singleton 
{
  INSTANCE;
}

As enums don’t have any constructor so it is not possible for Reflection to utilize it. Enums have their by-default constructor, we can’t invoke them by ourself. JVM handles the creation and invocation of enum constructors internally. As enums don’t give their constructor definition to the program, it is not possible for us to access them by Reflection also. Hence, reflection can’t break singleton property in case of enums.

2. Serialization: as explained above on serialization, how we avoided it
3. Clone: as explained above on Cloning, how we avoided it.

https://www.geeksforgeeks.org/prevent-singleton-pattern-reflection-serialization-cloning/

https://stackoverflow.com/questions/20421920/what-are-the-different-ways-we-can-break-a-singleton-pattern-in-java


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
//algorithm is fixed, but to make algo work subclasses need to implement readData and processData. to not allow algo getting overridden render method is declared final. 

public final void render(){
String data=null;
String pdata=null;
data=readData();
pdata=processData(data);
System.out.println(pdata);
}

public abstract String readData();
public abstract String processData(String data);
}

XMLDataRenderer will implement readData and processData differently from TextDataRenderer but the render algorithm remains same.

Points to remember:
* The template method in the super class calls the methods of the sub classes, instead the subclasses calls the template method of the super class.
* Template methods are techniques for code reuse because with this u can standardize the algo and defer the specific implementations to the subclass.

Adapter: makes in-compatible interfaces compatible.

Flyweight: it is structural design pattern. here instead of creating large no of similar objects, those are reused to save memory. This is useful when memory is a key concern. For every class there are two types of attributes: intrinsic(sharable) and extrinsic(non-sharable). Non sharable state is passed as parameters to methods. This reduces memory usage. 

Decorator: Widely used structural pattern, it adds dynamically the functionality to an object at runtime without affecting the other object. It adds additional responsibility to an object by wrapping it. So it is called wrapper.
* Add and remove additional functionalities or responsibilities to an object dynamically at runtime, without affecting the other objects.
* Usually these decorators are designed on component interface, so u can select the object that has to be decorated at runtime.
* Sometime adding additional responsibility to a class may not be possible by subclasssing it. Only available way of achieving it is using decorator.



Command Pattern:
https://www.baeldung.com/java-replace-if-statements




How to make post request fault tolerant and idempotent:
https://medium.com/@saurav200892/how-to-achieve-idempotency-in-post-method-d88d7b08fcdd


**Prototype:**
refers to creating duplicate object while keeping performance in mind. This type of design pattern comes under creational pattern as this pattern provides one of the best ways to create an object.
 implementing a prototype interface which tells to create a clone of the current object. This pattern is used when creation of object directly is costly.
For example, an object is to be created after a costly database operation. We can cache the object, returns its clone on next request and update the database as and when needed thus reducing database calls.
Prototype allows us to hide the complexity of making new instances from the client. The concept is to copy an existing object rather than creating a new instance from scratch, something that may include costly operations. The existing object acts as a prototype and contains the state of the object. The newly copied object may change same properties only if required. This approach saves costly resources and time, especially when object creation is a heavy process. One of the best available ways to create an object from existing objects is the clone() method. Clone is the simplest approach to implement a prototype pattern. However, it is your call to decide how to copy existing object based on your business model. 
example:
```
Prototype Design Participants
1) Prototype : This is the prototype of an actual object.
2) Prototype registry : This is used as a registry service to have all prototypes accessible using simple string parameters.
3) Client : Client will be responsible for using registry service to access prototype instances.

When to use the Prototype Design Pattern

When a system should be independent of how its products are created, composed, and represented and 
When the classes to instantiate are specified at run-time. 
For example, 
1) By dynamic loading or To avoid building a class hierarchy of factories that parallels the class hierarchy of products or
2) When instances of a class can have one of only a few different combinations of state. It may be more convenient to install a corresponding number of prototypes and clone them rather than instantiating the class manually, each time with the appropriate state.


import java.util.HashMap;
import java.util.Map;

public class Prototype {

    public static void main(String[] args) {
        ColorStore.getColor("blue").addColor();
        ColorStore.getColor("black").addColor();
        ColorStore.getColor("blue").addColor();
        ColorStore.getColor("black").addColor();

    }
}
abstract class Color implements Cloneable{

    protected  String colorName;
    abstract  void addColor();

    public Object clone(){

        Object clone=null;

        try{
            clone=super.clone();
        }catch(CloneNotSupportedException e){
            e.printStackTrace();
        }
        return clone;
    }
}

class BlueColor extends Color{

    public BlueColor(){
        this.colorName="blue";
    }

    void addColor(){
        System.out.println("Blue color added:"+this.hashCode());
    }
}

class BlackColor extends Color{
    public BlackColor(){
        this.colorName="black";
    }

    void addColor(){
        System.out.println("Black color added:"+this.hashCode());
    }
}

class ColorStore{
    private  static Map<String,Color> colorMap=new HashMap<>();

    static {
        colorMap.put("blue",new BlueColor());
        colorMap.put("black",new BlackColor());
    }

    public static Color getColor(String colorName){
        return (Color)colorMap.get(colorName).clone();
    }
}

```
