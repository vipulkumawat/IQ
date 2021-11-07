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

 
> public class DateUtil{
> private static DateUtil instance;
> private DateUtil(){}
> public static DateUtil getInstance(){
> if(instance==null){
> instance=new DateUtil();
> }
> return instance;
> }
> }
