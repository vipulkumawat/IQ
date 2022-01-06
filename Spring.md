
@Component:
•	If we want Spring to create and manage objects, we can do so by adding the @Component annotation at the beginning of the class and importing org.springframework.stereotype.Component.


@Autowired:
Spring needs to know is the dependencies of each object. The @Autowired annotation is used for this purpose and we need to import org.springframework.beans.foctory.annotation.Autowired to be able to use this annotation.

@ComponentScan:
Spring requires from the developer, is the location of the beans so that it can find them and autowire the dependencies. The @ComponentScan annotation is used for this purpose. This annotation can be used with or without arguments. It tells Spring to scan a specific package and all of its sub-packages. In our case, all the files that contain beans are in the same package, io.datajek.springbasics, so we want Spring to do a component scan on this package.

we are using Spring Boot, it uses the @SpringBootApplication annotation
This annotation is equivalent to the following three annotations:
•	@Configuration, which declares a class as the source for bean definitions
@EnableAutoConfiguration, which allows the application to add beans using classpath definitions
•	@ComponentScan, which directs Spring to search for components in the path specified



Because of @SpringBootApplication annotation, we do not need to use @ComponentScan annotation in our code.

@SpringBootApplication tells Spring to scan all the files in the package where the class with this annotation is present. It also scans any sub-packages of the package where it is placed.


•	The beans that Spring creates are managed by the Application Context. We can get information about a bean from the Application Context. The run method returns the ApplicationContext, which can be assigned to a variable appContext. Then the getBean method of ApplicationContext can be used to get the bean of a particular class. We will create a local variable recommender and assign the bean to it as follows:



public static void main(String[] args) {
    
    //ApplicationContext manages the beans and dependencies
    ApplicationContext appContext = SpringApplication.run(
                             
MovieRecommenderSystemApplication.class, args);

    //use ApplicationContext to find which filter is being used
    RecommenderImplementation recommender = appContext.getBean(
                                       
RecommenderImplementation.class);   
    
    //call method to get recommendations
    String[] result = recommender.recommendMovies("Finding Dory");
    
    //display results
 
   System.out.println(Arrays.toString(result));
}





Instead of us having to create an instance of the RecommenderImplementation class, Spring Application Context creates the beans. 

. A summary of the actions is reproduced below:

· Loading source class…
	The package is being searched. Spring starts with a component scan to find anything with @Component as well as other annotations that we will discuss in future lessons.
· Identified candidate component class…
	Spring identifies two candidates which have the @Component annotation as we only used it in two places in our code.
· Creating shared instance of singleton bean ‘movieRecommenderSystemApplication’
· Creating shared instance of singleton bean ‘contentBasedFilter’
	Spring starts creating instances of the beans. It creates beans that do not have any dependency first.
· Creating shared instance of singleton bean ‘recommenderImplementation’
	Autowiring by type from bean name ‘recommenderImplementation’ via constructor to bean named ‘contentBasedFilter’
	Now Spring can autowire the dependency using the constructor that we have provided and creates the RecommenderImplementation bean.
· To better understand these annotations, play around with the code below and see what error messages Spring throws when some of the annotations are missing. The error message can be found at the end of the log.
	If we remove @Component from the ContentBasedFilter class, Spring will throw an error when trying to autowire the dependency saying it required a bean of type Filter that could not be found.
	If we remove @Component from the RecommenderImplementation class as well, we will get an error when trying to execute the getBean method as no beans exist.
	If we add @Component to the CollaborativeFilter class, Spring will not know which bean of Filter type to autowire. It says, “expected single matching bean but found two”. We will see how to resolve this in the next lesson.
Autowiring By Type — @Primary
we will add another bean and see how Spring can dynamically choose a bean if it finds two matches of the same type.
NoUniqueBeanDefinitionException:
· We will add the @Component annotation on the CollaborativeFilter class to declare it a bean. Now both implementations of the Filter interface are beans. Previously, when Spring searched for a dependency to be autowired in the RecommenderImplementation object, it only found one bean of matching type. Now when we run the application, it fails to start.
The NoUniqueBeanDefinitionException occurs. The error message says: Required a single bean but two were found.


One way Spring can choose between two beans of the same type is by giving one bean priority over the other. The @Primary annotation is used for making a component the default choice when multiple beans of the same type are found.

Using @Primary is called autowiring by type. We are looking for instances of type Filter.
1. If we make both beans primary by adding the @Primary annotation to both implementations of the Filter interface, we will get an error. This happens because Spring doesn’t know which one to inject in the RecommenderImplementation object. The error message states “more than one ‘primary’ bean found among candidates".

Page: 24
Autowiring By Name
autowiring by name where we specify the bean that is to be used by name. In this approach, while creating an object, the dependency is injected by matching the name of the reference variable to the bean name. The developer has to ensure that the variable name is the same as its bean name.

When Spring finds two beans of the same type (Filter), it determines that the bean to inject is the one whose name matches the bean with the @Component annotation. In other words, the variable name (contentBasedFilter) matches the bean name (ContentBasedFilter).

3.	As an exercise, let’s see what happens if the bean name and variable names are different. Let’s change the name of the variable to filter.
When the application is run, autowiring does not take place and, as expected, we get the NoUniqueBeanDefinitionException.

4.	We have seen two autowiring approaches so far. To see which autowiring approach takes precedence, we will use the @Primary annotation on ContentBasedFilter class and use autowiring by name by changing the name of the variable of type Filter in RecommenderImplementation class to collaborativeFilter.
The application chooses the ContentBasedFilter bean, showing that @Primary has a higher priority.
This is because @Autowired annotation tries to resolve dependency by type first. If it fails to resolve a conflict and finds more than one bean of the same type then it tries to resolve it by name.

The autowiring by name approach is advantageous when we want to use one bean in one situation and another bean in some other situation. Using @Primary will always give preference to one bean, which is impractical if we want to use different beans in different scenarios. Autowiring by name ensures that if we have some other component which wants to use another type of bean, it can request Spring by using a different variable name.

Autowiring — @Qualifier
@Qualifier annotation#
Like @Primary, the @Qualifier annotation gives priority to one bean over the other if two beans of the same type are found. The bean whose name is specified in the @Qualifier annotation qualifies to be injected as a dependency. The @Qualifier annotation can be used in a scenario when we have multiple objects of the same type and autowiring by name cannot be used because the variable name doesn’t match any bean name.



2.	Say, we want to use the name CBF for ContentBasedFilter. We can either specify it in the @Component annotation or use @Qualifier annotation on the class. Both approaches, shown below, yield the same result:
@Component("CBF")
public  class ContentBasedFilter 
implements Filter{
    //...
}
@Component
@Qualifier("CBF")
public  class ContentBasedFilter 



@Autowired
    @Qualifier("CBF")
    private Filter filter;



Comparison with @Primary#
4.	The @Qualifier annotation takes precedence over the @Primary annotation. To show this, let’s add the @Primary annotation to the ContentBasedFilter class and run the application.



. This is because @Primary is the default setting, while @Qualifier is specific. @Primary defines the default selection when no other information is available. It tells Spring to use the bean marked as primary as its first choice if it encounters more than one bean of the same type. On the other hand, @Qualifier tells Spring to use a specific bean if it finds multiple beans of matching type.





@Primary annotation should be used if there is one clear favorite to be used in a majority of situations. In some cases, one algorithm might be more efficient or more important than the rest and is declared as the primary choice. The bean with @Primary gets chosen unless another bean is required, which can be specified with @Qualifier. The bean with @Qualifier is only used to request an “alternate” bean in case the primary choice is not required.
@Autowired annotation resolves dependencies by type. If there are more than one beans of the same type, a conflict arises. We have seen three different approaches to resolve conflicts. They can be resolved using the @Primary annotation, renaming the variable to match the name of the class, or by using the @Qualifier annotation.



Constructor and Setter Injection:
Spring framework gives the developer control over how beans are wired in. There are a variety of options to choose from. We will focus on constructor injection and _setter injection.


Dependency injection:
We will use the @Autowired annotation at different places in the code to direct Spring which injection type to use.
Autowiring the dependency using a constructor is called constructor injection. 


Default bean name is the class name with the first letter in lowercase.

To use constructor for injecting dependencies, we can move the @Autowired annotation to the constructor. 


The @Qualifier annotation cannot be used on the constructor (as it results in an error message: “The annotation @Qualifier is disallowed for this location”), rather, it should be used in the argument list right in front of the property that we want to be autowired 

@Autowired
public RecommenderImplementation(@Qualifier("collaborativeFilter") Filter filter) {}

It should also be noted that the use of the @Autowired annotation is optional when using constructors.


6.	Another way to wire in a dependency is by using a setter method. We will create a setter method 

7.	We can guide Spring to use the setter method by using the @Autowired annotation before the method. 

Field injection
9.	We have seen two dependency injection methods above but Spring was already performing dependency injection without a constructor or setter method
We have been using @Autowired annotation directly on the Filter field. This is called field injection

Using field injection keeps the code simple and readable, but it is unsafe because Spring can set private fields of the objects. Testing also becomes inconvenient because we need a way to perform dependency injection for testing. Yet another disadvantage is that a developer may add a lot of optional dependencies which can make the application complex. If there was a constructor, then each additional dependency would result in increasing the number of arguments of the constructor.


Both constructor and setter injection result in the same outcome. However, there are some differences. Setter injection is more readable as it specifies the name of the dependency as the method name but the number of setter methods increases with each increasing dependency increasing the boiler plate code. Setter injection is used to avoid the BeanCurrentlyInCreationException raised in case of a circular dependency, because unlike constructor injection where dependencies are injected at the time when context is loaded, setter injection injects dependencies when they are needed.
Constructor injection ensures that all dependencies are injected because an object cannot be constructed until all its dependencies are available. It also ensures immutability as the state of the bean cannot be modified after creation.




Bean Scope
The Spring container manages beans. The term bean scope refers to the lifecycle and the visibility of beans. It tells how long the bean lives, how many instances of the bean are created, and how the bean is shared.
Types of bean scopes#
There are six types of scopes: singleton, prototype, request, session, application, and websocket.


Types of bean scopes
The singleton and prototype scopes can be used in any application while the last four scopes are only available for a web application.


Singleton scope#
The default scope of a bean is singleton, in which only one instance of the bean is created and cached in memory. Multiple requests for the bean return a shared reference to the same bean. In contrast, prototype scope results in the creation of new beans whenever a request for the bean is made to the application context.


Singleton scope
Singleton bean scope is the default scope. It is used to minimize the number of objects created. Beans are created when the context is loaded and cached in memory. All requests for a bean are returned with the same memory address. This type of scope is best suited for cases where stateless beans are required. On the contrary, prototype bean scope is used when we need to maintain the state of the beans.


@Scope("Prototype")
@Scope(ConfigurableBeanFactory.SCOPE_PROTOTYPE)
application context will create a new object every time we invoke the getBean() method.


Spring creates a singleton bean even before we ask for it while a prototype bean is not created till we request Spring for the bean. 
When the application is run, the output shows that Spring has created a Singleton bean but the Prototype bean has not yet been created

Page33


singleton bean constructor is called only once while the prototype bean constructor is called for every requst.

difference between the Spring singleton and the Gang of Four (GoF) singleton design patterns. The singleton design pattern as specified by the GoF means one bean per JVM. However, in Spring it means one bean per application context. By the GoF definition, even if there were more than one application contexts running on the same JVM, there would still be only one instance of the singleton class.

Mixing Bean Scope
Singleton bean with prototype dependency#
Now that we understand the concept of singleton and prototype bean scopes, we can move on to an interesting problem of mixing bean scopes. Sometimes, a bean has singleton scope but its dependency has prototype scope.

The ContentBasedFilter bean has singleton scope because we need only one instance of the filter. However, the Movie bean has prototype scope because we need more than one objects of this class.


@Component
public class ContentBasedFilter 
implements Filter {
    //for keeping track of instances created
    private static int instances= 0;
 
    @Autowired
    private Movie movie;

    public ContentBasedFilter() {
        super();
        instances++;
     
System.out.println("ContentBasedFilter constructor called");
    }

    public Movie getMovie() {
        return movie;
    }

    public static int getInstances(){
        return ContentBasedFilter.instances;
    }
}






public static void main(String[] args) {
    ApplicationContext appContext = SpringApplication.run(
                                        
MovieRecommenderSystemApplication.class, args);

    //Retrieve singleton bean from application context
    ContentBasedFilter filter = appContext.getBean(ContentBasedFilter.class);   
 System.out.println("\nContentBasedFilter bean with singleton scope");
    System.out.println(filter);
    
    //Retrieve prototype bean from the singleton bean thrice
    Movie movie1 = filter.getMovie();   
    Movie movie2 = filter.getMovie();   
    Movie movie3 = filter.getMovie();
    
    System.out.println("\nMovie bean with prototype scope");
    System.out.println(movie1);
    System.out.println(movie2);
    System.out.println(movie3);

    //Print number of instances of each bean
 System.out.println("\nContentBasedFilter instances created: "+ 
                     
 ContentBasedFilter.getInstances());
 System.out.println("Movie instances created: "+ Movie.getInstances());
}





We expect one instance of ContentBasedFilter bean and three instances of the prototype Movie bean but the output is different, as can be seen by running the following code:





The output of the above code widget shows that the same Movie bean is returned every time. Moreover, the number of instances of the prototype bean created is one instead of three. As mentioned in the previous lesson, a singleton bean is created when the context is loaded. The Movie constructor was called by Spring when it was creating the ContentBasedFilter bean. The prototype bean is injected into the singleton bean at the time of creation of the singleton bean when the container initializes it. This explains the following messages in the output:
***
When a prototype bean is injected into a singleton bean, it loses its prototype behavior and acts as a singleton.


The same instance of the bean is returned by the application context every time it is requested using the getMovie method.
Prototype bean acting as a singleton bean is wired in at the time of container initialization


Proxy#
5.	Right now, Spring cannot inject the prototype bean into the singleton bean after it has been created. This problem can be solved in a number of ways. One of them is by using a proxy. We declare the bean with prototype scope as a proxy using the proxyMode element inside the @Scope annotation.
@Scope(value=ConfigurableBeanFactory.SCOPE_PROTOTYPE, proxyMode=ScopedProxyMode.TARGET_CLASS)


The prototype bean doesn’t get autowired into the singleton bean at the time of its creation. Instead, a proxy or placeholder object is autowired. The proxy adds a level of indirection. When the developer requests the prototype bean from Spring, a new instance of the prototype bean is created and is returned by the application context. The proxy mode allows Spring container to inject a new object into the singleton bean.
Proxy injected in place of prototype bean


As can be seen from the output, the singleton bean constructor is called when the ContentBasedFilter object is initialized, but the Movie constructor isn’t called at that time. The Movie constructor is called whenever the getMovie() method is called.

@Lookup#
6.	Another method is by using the @Lookup annotation on the getMovie() method. This annotation tells Spring to return an instance of Movie type. It is essentially the same as beanFactory.getBean(Movie.class).


One thing to consider is that singleton scope minimizes the number of objects created so the scope should only be changed where necessary. If there are more objects, there will be an impact on the memory used as well as on garbage collection.

@ComponentScan
Spring does a component scan to search for the beans that it manages. In a Spring application, the @ComponentScan annotation without any argument tells Spring to scan the current package as well as any sub-packages that might exist. Spring detects all classes marked with the @Component, @Repository, @Service, and @Controller annotations during component scan.

In a Spring application, @ComponentScan is used along with the @Configuration annotation. In a Spring Boot application, component scan happens implicitly. The @SpringBootApplication annotation is a combination of three annotations:
•	@Configuration
•	@EnableAutoConfiguration
•	@ComponentScan
'SpringBootApplication' combines three annotations
@SpringBootApplication by default, searches the package where it is present, as well as all the sub-packages. If a bean is present in a package other than the base package or its sub-packages, it will not be found. If we want Spring to find beans defined in other packages, we need to use the @ComponentScan annotation and provide the path of the package where we want Spring to look for the beans.



        ApplicationContext appContext = SpringApplication.run(MovieRecommenderSystemApplication.class, args);

        System.out.println("ContentBasedFilter bean found = " + appContext.containsBean("contentBasedFilter"));


The containsBean method, which returns a Boolean value, is used to check if the bean is found during component scanning.



@ComponentScan(basePackages = {"package1","package2"})

4.	@ComponentScan can be used to include or exclude certain packages from being scanned. Include filters are used to include certain classes in component scan. Exclude filters are used to stop Spring from auto-detecting classes in component scan.

Filter types#
There are different types of filters that make use of stereotype annotations, interfaces, regular expressions, and AspectJ expressions. Spring also allows the creation of custom filters, e.g., find only those beans whose names are a certain length. FilterType can have the following values:
•	FilterType.ANNOTATION
•	FilterType.ASPECTJ
•	FilterType.ASSIGNABLE_TYPE
•	FilterType.REGEX
•	FilterType.CUSTOM
One way to direct Spring to detect both ContentBasedFilter and CollaborativeFilter beans, is to use the include filter of type REGEX and provide the path of the package where the ContentBasedFilter bean is present.


@ComponentScan(basePackages = "io.datajek.spring.basics.movierecommendersystem.lesson10")
@ComponentScan(includeFilters = @ComponentScan.Filter (
                    type= FilterType.REGEX,                     pattern="io.datajek.spring.basics.movierecommendersystem.lesson9.*"))


Our REGEX pattern evaluates to all beans declared with @Component annotation in the lesson9 package. Now when the application is run, beans from two different packages are successfully detected.

Bean Lifecycle: @PostConstruct, @ PreDestroy

Spring manages the entire lifecycle of beans from the time they are created till the time they are destroyed. It provides post-initialization and pre-destruction callback methods on the beans. The developer can tap into these callbacks and write custom initialization and cleanup code.


4.	When Spring creates a bean, the first thing it does, is to autowire the dependencies. If the developer wants to perform a task after the dependencies have been populated, it can be done by calling a method annotated with the @PostConstruct annotation. A method with this annotation works like the init method. The @PostConstruct annotation tells Spring to call the method for us once the object has been created. The method can have any name and its return type is always void. After the bean is created, we can initialize the contents of the bean, load data, establish a database connection, or connect to a web server. The post construct method is only called after all the dependencies have been populated.



The constructor of the ContentBasedFilter class is called. After the constructor method, the PostConstruct method is called. When the bean has been created, it is injected into the RecommenderImplementation bean as can be seen from the logger output of the setter method. After the dependency has been injected into the RecommenderImplementation bean, its PostConstruct method is called. Now the bean is ready for use and is returned by the getBean() method after which the bean name is printed.

@PreDestroy#
7.	The callback method that is executed just before the bean is destroyed is annotated using @PreDestroy. The method having this annotation is called when the bean is in the process of being removed from the container. All cleanup stuff can be performed in this method. A method with the @PreDestroy annotation can be used to release resources or close a database connection.


Bean Lifecycle: Prototype Scoped Beans
Lifecycle of prototype beans#
Spring manages the entire lifecycle of singleton beans but it does not completely manage the lifecycle of prototype beans. This is because there might be a large number of prototype instances and the container can become overwhelmed keeping track of them.
The Spring container creates the prototype beans and hands them over when requested. Thereafter, it is the responsibility of the application to destroy the bean and free up any resources that it has acquired.



the post initialization method is called but the pre-destruction method is not called for prototype beans. This class has prototype scope

we can see that the constructor and post construct methods of the singleton bean are called when the bean is created, before the application starts.
The prototype bean is not created beforehand and the constructor and post construct methods for the prototype bean are only called when we request the application context for the prototype bean.

When the application terminates, the PreDestroy method is called for the singleton bean but not for prototype scoped bean


Contexts and Dependency Injection Framework
Contexts and Dependency Injection (CDI) is an interface that standardizes dependency injection for Java EE. It defines different annotations for dependency injection like @Named, @Inject, @Scope, @Singleton, etc. Different CDI implementation frameworks provide support and functionality for these annotations.
@Named is used to define a bean and @Inject is used for autowiring one bean into another. 

To be able to use CDI annotations in our Spring application, we need to add a dependency 

<dependency>
    <groupId>javax.inject</groupId>
    <artifactId>javax.inject</artifactId>
    <version>1</version>
</dependency>


***
we can replace the @Component and use @Named to declare components.


@Inject:
4.	Spring has the @Autowired annotation for dependency injection but it also supports the equivalent CDI annotation, @Inject. 


6.	Other annotations provided by CDI are @Qualifier, @Scope, and @Singleton. The @Qualifier annotation is similar to the one we have seen in Spring and is used to break ties if two beans of the same type qualify to be injected in a dependency.



@Scope is used to set the scope of the bean, similar to the @Scope annotation in Spring. The @Singleton annotation is used to explicitly set the scope to singleton in CDI annotation. In Spring, we can specify singleton scope using the @Scope annotation.


2.	spring-core provides the fundamental features of Spring framework like dependency injection and Inversion of Control.


spring-core defines the bean factory and forms the base of the Spring framework.


spring-context dependency#
3.	To be able to use ApplicationContext, we need to add another dependency called spring-context as follows:


<dependency>
 <groupId>org.springframework</groupId>
 <artifactId>spring-context</artifactId>
</dependency>


7.	Spring Boot automatically closes the application context in the end, but now we need to close the context as follows:
//close the application context
appContext.close();



The changes that we made in this lesson that enabled us to run a Spring Boot application as a basic Spring application are as follows:
•	Removing the spring-boot starter dependency and replacing it with spring-core and spring-context.
•	Replacing @SpringBootApplication with @Configuration and @ComponentScan.
•	Replacing the SpringApplication class with the AnnotationConfigApplicationContext class.




Stereotype Annotations:
Beans can be declared using the @Bean annotation in a configuration class or by using the @Controller, @Service, and @Repository annotations. These annotations are used at different layers of an enterprise application.

@Component is a generic annotation. It can be used in any layer, if the developer is unsure about where the bean belongs. The other three annotations, @Controller, @Service, and @Repository, are specific to layers.


@Controller#
@Controller is used to define a controller in the web layer. Spring scans a class with @Controller to find methods that are mapped to different HTTP requests. 

. @RestController is a specialized form of @Controller.


@Service#
@Service is used in the business layer for objects that define the business logic. It marks a class as a service provider.


@Repository#
@Respository is used in the data layer to encapsulate storage, retrieval, and search in a typical database. This annotation can also be used for other external sources of data.



The advantage of having annotations specific to every layer instead of the generic @Component is in Aspect Oriented Programming (AOP). We can identify the annotations and add functionality to specific annotations. Similarly, we can classify components in different categories and apply a specific logic to each category. For example, if we want to log everything that is coming from the business layer, we can identify objects with the @Service annotation using AOP and log all the content.



Spring provides a default exception translation facility for JDBC exceptions if the @Repository annotation is used. This feature cannot be used on beans annotated with @Component. When using a persistence framework like Hibernate, exceptions thrown in a class with the @Repository annotation are caught and automatically translated into Spring’s DataAccessException class.




the request mapping feature is enabled only when using the @Controller annotation. The DispatcherServlet automatically looks for @RequestMapping for classes marked with the @Controller annotation only.



The @Controller, @Service, and @Repository annotations are similar to @Component annotation with respect to bean creation and dependency injection, except that they provide specialized functionality.



Using an External Property File:
We can now dynamically fetch value from the application properties file using the @Value annotation.

If the property value is not found in app.properties file, Spring throws the IllegalArgumentException. One way to avoid this exception is to provide a default value for the property:


@Value("${recommender.implementation.favoriteMovie: Finding Dory}")
String favoriteMovie;


we will mention the name of the file from where to fetch the value using the @PropertySource annotation. By default, Spring loads the property file from the classpath. Since our file is in src/main/resources, we will use classpath:app.properties.




What is Spring Boot?
Spring boot enables robust creation of applications. It provides features like servers, metrics, heath checks, etc. Spring Boot allows for integration with many different servers, but by itself, it is neither an application server nor a web server. Auto configuration is a great feature of Spring Boot whereby it provides all the required dependencies to start a particular project. For example, starter web automatically configures everything needed for a web application. Similarly, starter JPA automatically configures basic JPA along with Hibernate. The main features of Spring Boot are shown below:


Spring Boot autoconfiguration#
Page 54:



Springboot Autoconfiguration:
Spring Boot configures appropriate versions of Spring core, dispatcher servlet, view resolver, logging, security and validation frameworks along with exception handling and support for internationalization. Spring Boot takes care of the configuration part for us so we can focus on developing the business logic. Spring Boot saves the time spent on creating a Spring application from scratch.


Starter web is the preferred starter for building web applications, including RESTful applications, using Spring MVC. It uses Tomcat as the default embedded container. The pom.xml file of spring-boot-starter-web shows a number of dependencies including spring-web, spring-webmvc, starter-tomcat, and starter-json for conversion to JSON when a web service is invoked.


Starter test is the starter dependency for testing Spring Boot applications with libraries including JUnit Jupiter, Hamcrest, and Mockito. spring-boot-starter-test enables the developer to write unit and integration tests. The pom.xml file shows dependencies on JUnit, AssertJ, and Mockito. It also has Hamcrest that, in combination with AssertJ, is used for writing matchers.


Starter JPA is another frequently-used starter project. JPA is the interface for the Hibernate framework. starter-data-jpa is used for Spring Data JPA with Hibernate. The pom.xml file shows that it has a dependency on spring-boot-strater-aop, spring-boot-starter-jdbc, hibernate-core, and transaction-api.


Spring Boot offers a Developer Tool that supports live reloads. This jar is provided by the Spring Boot framework and is useful for development-specific debugging. To use developer tools

<dependency>
 <groupId>org.springframework.boot</groupId>
 <artifactId>spring-boot-devtools</artifactId>
</dependency>



If the scope of this dependency is limited to runtime, it will not be packaged in the jar.


Automatic restart#
One of the things that you will notice when running the application after making a change in the code is that the application automatically starts again. This is an efficient restart that takes way less time as compared to a typical restart. Spring knows that the Maven dependencies do not change, so only the application beans are loaded again, which is why it takes less time.



DevTools causes an automatic restart when a file on its classpath changes. Spring Boot provides two classloaders: one for the classes that do not change like third-party jars and the other for application code using the RestartClassLoader. When the code is changed, only the RestartClassLoader is loaded, which causes the restart to be much faster.


LiveReload server:
Spring Boot comes with a LiveReload embedded server which triggers an automatic browser refresh. The LiveReload extensions are available for different browsers. Once installed and enabled, any change in the code is detected by the LiveReload server and the browser is automatically refreshed to reflect the change.


Actuator:
provides monitoring features for the application during development and after deployment. It provides metadata about the application like the beans configured, how autoconfiguration has worked, how many times a specific service is called, how many times a specific service has failed, etc

The Actuator exposes a lot of REST services that are compliant with the HAL standard. We will use a HAL browser to view the data provided by the services. For this, add the following dependency:
<dependency>
      <groupId>org.springframework.data</groupId>
    <artifactId>spring-data-rest-hal-browser</artifactId>
    <version>3.3.6.RELEASE</version>
</dependency>


To enable the web exposure of all management endpoints, add the following line to application.properties:

management.endpoints.web.exposure.include=*


/beans` shows all the spring beans that are configured. It shows the name of the bean as well as scope and type, and any dependencies that the bean might have. It can be used to analyze the application.

•	/condition shows all the positive and negative matches for autoconfiguration similar to the report that is generated at application startup.
•	/httptrace shows the last 100 requests that were executed along with the response that was sent back.
•	/mappings shows all the URI’s for @RequestMapping



•	/metrics shows a list of valid metrics. Further information about any metric can be obtained by copying the metric and adding it to the url. For example, the jvm.memory.used will show the amount of memory used.
•	/shutdown when enabled, lets the application gracefully shutdown. The feature can be enabled by making the following changes to the application.properties file:
management.endpoint.shutdown.enabled=true




It should be noted that enabling a lot of tracking and monitoring has an impact on performance. For example, enabling httptrace for all requests will hamper performance. Also, careful consideration is required when enabling endpoints since they expose sensitive information about the application.


Spring MVC is an HTTP oriented Spring framework, which is concerned with developing web applications. It makes use of the Model View Controller (MVC) design pattern to achieve separation of concerns.


MVC Architecture
The DispatcherServlet is the front controller that handles all requests while the View Resolver is concerned with resolving view names to physical views. This decoupling makes development of web applications and RESTful services very simple because the model, view, and controller operate without dependency. When we built a web service with Spring Boot, it internally made use of Spring MVC. Spring MVC helps create web applications that are scalable as well as testable.


Spring Boot#
Spring Boot is designed to solve configuration issues. It autoconfigures a lot of dependencies based on the kind of application that is being built. Spring Boot offers pre-configured projects to bootstrap an application in a few simple steps. When building a web application using Spring Boot, the DispatcherServlet, ViewResolver, Data Source, Transaction Manager, etc. get configured automatically. Spring Boot configures compatible versions of the dependencies needed for the frameworks. As we saw in the last lesson, it also provides monitoring features.
Spring Boot helps kickstart the project by bringing in all the required dependencies. It is a useful tool for someone who is just starting out with Spring and gets overwhelmed with the configuration part. It also saves a lot of time. However, Spring Boot offers a biased view and has strong preferences about the dependencies that are used.








Pg: 60

Creating a JDBC Starter Project:
The in-memory database H2 has automatically been configured in our application.

spring.datasource.url=jdbc:h2:mem:testdb


spring.h2.console.enabled=true

create an SQL file in src/main/resources called schema.sql. This file will be called whenever the application is launched and will initialize the database. It contains all the DDL (Data Definition Language) queries.

Spring provides JdbcTemplate, which makes it easy to write and execute a query. It also provides the BeanPropertyRowMapper which maps rows of a table to a bean.


A CommandLineRunner is an interface in Spring Boot which has only one method called run. This method is launched as soon as the context is loaded.


 JdbcTemplate takes out the common functions required before and after the execution of a query so the developer only focuses on the query and any custom result set retrieval functionality. JdbcTemplate creates the connection and automatically closes it if an exception is thrown.
We have an embedded database in our classpath. Spring Boot autoconfiguration sees the database and autoconfigures a datasource. This leads to a JdbcTemplate getting autoconfigured.



we have used the BeanPropertyRowMapper to map the results of the query to our bean. If the database table has a different structure or column names, we need to define our custom mapping.


RowMapper interface#
1.	We can define our own row mapper by implementing the RowMapper interface and providing the bean onto which the rows will be mapped. The custom row mapper, PlayerMapper is created as an inner class because it will only be used inside JdbcPlayerDao. It is best practice to make it static and final.



70

Custom RowMapper:
we have used the BeanPropertyRowMapper to map the results of the query to our bean. If the database table has a different structure or column names, we need to define our custom mapping.


We can define our own row mapper by implementing the RowMapper interface and providing the bean onto which the rows will be mapped. The custom row mapper, PlayerMapper is created as an inner class because it will only be used inside JdbcPlayerDao. It is best practice to make it static and final.


mapRow method#
2.	The Rowmapper interface has one method, mapRow, for which we will write our custom implementation to initialize a Player object. This method defines how a row is mapped. It takes two arguments, the first being the result set which JdbcTemplate gets after running the query and the second being the row number. The row number of every row in the result set is different. The JdbcTemplate calls the mapRow method for every row in the result set and passes its row number as an argument. 


JDBC requires the developer to write the queries, map values to the query, pass a set of parameters to execute the query, and map rows of the result set to a bean.

For simple queries like the one we implemented in the Spring JDBC section, this task is manageable, but in large applications with hundreds of tables, the queries become complex. Writing and maintaining those queries requires expertise beyond the skillset of a Java developer. Java Persistence API (JPA) is designed to ease that task.
How JPA works#
JPA challenges the notion of writing queries and mapping the data back. It creates entities that are Java objects which map to a row in a database table.

JPA creates a schema based on the entities and defines relationships between entities. The Object-Relational Mapping (ORM) layer maps the objects to a database table



ORM maps Java objects to table rows
Using JPA, we can map a Java class or bean to a table. The members of the class map columns in the table. When this mapping is defined, JPA can write queries on its own. It takes the responsibility of creating and executing queries for CRUD operations. This is due to the fact that the operations performed on a database are identical and can be generalized. The types of objects change based on the database schema but the operations remain the same.
Class members are mapped to columns in a database table
JPA implementations#
Hibernate, the most popular ORM framework in the last decade, prompted the creation of the JPA standard. JPA is a standard of Object Relational Mapping. It is an interface that defines a set of annotations for creating the object relational mapping. There are numerous implementations of the JPA interface like Hibernate, EclipseLink, Apache OpenJPA, etc. Hibernate is by far the most popular implementation of JPA. It is a lightweight framework and can easily be integrated with Spring.
The benefit of using JPA instead of Hibernate is that JPA is a standard and one can switch to any other implementation later.




JPA API  defines a lot of different annotations like @Entity, @Column, @Table, etc. Hibernate is an implementation of the JPA API which automatically gets configured in our application. 



@Entity
@Table
@Id
@GeneratedValue

. We will use the @Entity annotation to map this class to the Player table.

In case we want to map this class to a table with a different name, we can use the @Table annotation and provide the name of the table to which the bean maps to

Since the name of the entity and table match, we do not need the @Table annotation.


The @Id annotation is used to indicate the primary key. We can also let JPA generate the primary key value when we insert rows. The @GeneratedValue annotation will automatically generate Id values.


Now whenever a new row is inserted, we do not need to supply the Id value. We need another constructor that initializes all attributes except Id.


JPA schema creation#
4.	The Spring Boot autoconfiguration triggers a schema update and creates a table by the same name as the class marked with the @Entity annotation. When using JPA, we do not need to create a table. We will comment out the table creation query in schema.sql as it is not needed anymore.



@Repository 

Enabling transaction management#
2.	Database queries contain multiple steps. We will also enable transaction management to allow all steps in a query to succeed. In case of an error or runtime exception, all steps will be rolled back. Transactions are implemented at the business layer, but in this example, we will implement them at the repository level. Spring provides all the boilerplate code to start, commit, and roll back a transaction, which can also be integrated with JPA’s transaction management. This is enabled using the @Transactional annotation on a method or a class.


@Repository
@Transactional
public class PlayerRepository{

}   
Using this annotation on the PlayerRepository class, all the methods will be executed in a transactional context. So if we have INSERT and UPDATE in a single method, something called an EntityManager will keep track of both of them. If one of them fails, the whole operation will be rolled back.
EntityManager and @PersistenceContext annotation#
3.	A JPA EntityManager manages connection to a database as well as to database operations. EntityManager is associated with a PersistenceContext. All operations that are performed in a specific session are stored inside the PersistenceContext. EntityManager is the interface to the Persistence Context. All operations on the entity go through the EntityManager. We will declare an EntityManager object in our class and mark it with the `@PersistenceContext annotation.



public class PlayerRepository{
    @PersistenceContext
    EntityManager entityManager;
    //...
}
EntityManager provides a number of methods that perform SELECT, INSERT, UPDATE, and DELETE queries


Executing a query#
We will use the CommandLineRunner interface to use the run method




show-sql property#
We have inserted two rows in the database without writing any queries. To see the queries that Hibernate has generated, we can enable the show-sql property in the application.properties file as follows:
spring.jpa.show-sql=true





JPQL Named Query:
A named query is defined on an entity

To create a named query, we will use the @NamedQuery annotation on the Player class. This annotation requires two parameters: the name of the query and the query itself. When using JPA, we will write the query in JPQL instead of SQL. JPQL uses entities in place of tables.


@Entity
@NamedQuery(name="get_all_players", query="select p from Player p")
public class Player {}

Using a named query for SELECT * query#
In the getAllPlayers method, we will use the createNamedQuery method. We need to pass the name of the query and specify what the query will return. The name of the query as defined in the previous step is get_all_players. This query will return objects of the Player class. The createNamedQuery returns a TypedQuery, which we will assign to a variable called getAll. Then, we can use the getResultList method to return a list of players 




public List<Player> getAllPlayers() {
    TypedQuery<Player> getAll = entityManager.createNamedQuery("get_all_players", Player.class);
    return getAll.getResultList();
}



Spring Data JPA:
The methods that we implemented as part of the CRUD operations are all generic methods. The logic of the methods remains the same, and only the entity changes.
Spring Data identified this duplication of code when writing repositories and created some predefined repositories. The developer provides the entity type and its primary key and Spring Data comes up with the CRUD methods for the entity. Spring Data JPA adds a layer of abstraction over the JPA provider (Hibernate in our case).




The JpaRepository interface extends the Repository interface. It contains the API provided by CrudRespository as well as the PagingAndSortingRepository for CRUD opretaions along with pagination and sorting of records.


JpaRepository interface#
1.	We will create an interface that extends the JpaRepository. We will call this interface PlayerSpringDataRepository. We need to specify the entity that will be managed by this repository, as well as the primary key of the entity as follows:
import org.springframework.data.jpa.repository.JpaRepository;

public interface PlayerSpringDataRepository extends JpaRepository<Player, Integer>{

    //no implementation required!
}



save method#
3.	To insert and update an object, Spring Data has a save method that works in the same manner as the merge method of the EntityManager.



findById method#
4.	Spring Data has a method called findById, which takes in the primary key and returns an object.

findAll method#
5.	It also has a findAll method which returns all entity objects.


deleteById method#
6.	For deletion, Spring Data has a deleteById method that takes the primary key of the record to be deleted.

Using Spring Data, we can run the same application again without writing an implementation for any of the CRUD operations. The JpaRepository provides us with methods needed to perform those operations. This results in a significant reduction in boilerplate code


The CRUD methods in Spring Data are annotated with @Transactional. Spring Data can parse a method name and create a query from it.

***
In the code widget below, we have a method findByNationality for which we have not provided any implementation. This method name is converted to the following JPQL query using the JPA Criteria API:
select p from Player p where p.nationality = ?1

We can use keywords such as And, Or, GreaterThan, LessThan, Like, IsNull, Not etc., in the method name and OrderBy clause can be used to sort the results.

****



Developing REST services in Spring. Spring provides specialized annotations that make RESTful application development easy. Some examples include @RestController, @ResponseBody and @ResponseStatus etc.
Spring also automatically handles Jackson integration which makes conversion of data from JSON to POJO and vice versa a breeze. Any JSON data received by the controller is automatically converted to a POJO and any POJO returned by the controller is converted to JSON.



What is REST?#
REST stands for the REpresentational State Transfer. It provides a mechanism for communication between applications. In the REST architecture, the client and server are implemented independently and they do not depend on one another. REST is language independent, so the client and server applications can use different programming languages. This gives REST applications a lot of flexibility.
 
REST request response
The REST architecture is stateless meaning that the client only manages session state and the server only manages the resource state. The communication between the client and server is such that every request contains all the information necessary to interpret it without any previous context.
Both the client and server know the communication format and are able to understand the message sent by the other side. REST calls can be made over HTTP. The client can send HTTP request message to the server where it is processed and an HTTP response is sent back.




REST request response
The request message has three parts:
1.	The request line contains the HTTP method like (GET or POST etc.)
2.	The request header contains data with additional information about the request.
3.	The request body contains the contents of the message so if it is a POST request, the request body will contain the contents of the entity to be created.
The response message also has three parts:
1.	The response line contains the status code for success or redirection etc.
2.	The response header contains additional information about the response like the content type and the size of the response. The client can render the data based on the content type so if it is text/html, it is displayed according to the HTML tags and if it is application/json or application/xml, it is processed accordingly.
3.	The response body contains the actual message sent in response to the request.
The HTTP methods for CRUD operations are:
•	POST for creating a resource
•	GET for reading a resource
•	PUT for updating a resource
•	DELETE for deleting a resource
JSON Data Binding




A Java object (POJO) can be converted into JSON and vice versa through a process called data binding. We can read a JSON string and use it to populate a Java object. In the same manner, we can use a Java object to create a JSON string.
Jackson Project#
Jackson Project handles data binding between Java and JSON. it also provides support for data binding with XML. Spring framework uses the Jackson project for data binding. 




Jackson handles the conversion between JSON and POJOs by making use of the getter and setter methods of a Java object. To convert a JSON string to a POJO, it calls the setter methods to populate the members. To create a JSON string from a POJO, it calls the getters methods. Jackson has access to the getters and setters only, not the private fields of the class.




It calls the corresponding setter methods to create a POJO from JSON string. If a setter method matching a JSON property is not found, an exception is thrown.



Creating a POJO from JSON
The Jackson annotation @JsonIgnoreProperties can be used to bypass the exception by setting the IgnoreUnknown attribute to true. This feature is useful when the JSON file contains more properties but we are only interested in a few of them.


REST API Design:
To create a REST API in Spring, we need the spring-webmvc dependency. This dependency supports web as well as RESTful applications. It loads all the supporting dependencies like spring-core, spring-context, spring-web etc., and comes with the embedded Tomcat server.




we need the jackson-databind dependency for JSON data binding. By having the Jackson dependency on the classpath, Spring will automatically handle the conversion of JSON data to POJO and vice versa.
Spring Boot makes the task of adding required dependencies easy. We can create a Spring Boot project from start.spring.io and add the starter dependency for Web. The spring-boot-starter-web takes care of both the dependencies mentioned above.



spring-webmvc and spring-boot-starter-json are included along with other dependencies like spring-boot-starter-tomcat


The @Id and @GeneratedValue annotations are used to mark the primary key and define the manner in which values are generated. By default, dates are saved as Timestamp by Hibernate. When we annotate the birthDate with @JsonFormat, Jackson will use the provided format for serializing and deserializing the field.


Database Initialization#
Hibernate can generate the DDL based on the spring.jpa.hibernate.ddl.auto property. We will use create-drop as its value 



The spring.jpa.show-sql property, when set to true, shows the queries used by Hibernate when creating the database. The database is populated using the import.sql file placed at the root of the classpath. 


use the @Service annotation to indicate that this class belongs to the service layer.


@RestController annotation. This annotation is an extension of @Controller annotation 
The @RestController annotation has support for REST requests and responses and automatically handles the data binding between the Java POJOs and JSON


@GetMapping
The client sends an HTTP request to the REST service. The dispatcher servlet handles the request and if the request has JSON data, the HttpMessageConverter converts it to Java objects. The request is mapped to a controller which calls service layer methods. The service layer delegates the call to repository and returns the data as POJO. The messageConverter converts the data to JSON and it is sent back to the client.


The REST API will automatically convert that list of POJOs to JSON when it finds Jackson on the classpath and a JSON response is returned to the client.

The @GetMapping annotation maps HTTP GET requests to controller methods. It is a shortcut for:
@RequestMapping(method = RequestMethod.GET)



@PathVariable:

4.	Since there is a path variable in the endpoint, we need to bind it with a method parameter. The @PathVariable annotation binds the path variable {id} from the URL to the method parameter id. 



getOne#
Alternatively, the JpaRepository provides the getOne method which returns an object. This method throws an EntityNotFoundException if the object does not exist. When using this method, we explicitly need to check for null values


@PostMapping
96



@PostMapping:
save : 
To distinguish between an INSERT and UPDATE operation, the save method checks the primary key of the object that is being passed to it. If the primary key is empty or null, an INSERT operation is performed, otherwise an UPDATE to an existing record is performed.

@RequestBody#
The client will send the player data in the request body as JSON. We will use Jackson to access the request body and convert the incoming JSON data to POJO. The @RequestBody annotation handles this conversion and binds the data in the request body to a method parameter.


The @RequestBody annotation binds the JSON from the request to the Player object. It converts the JSON to POJO without us having to parse the request body. We can directly use the data in the player object now.

@PatchMapping
Partial update
The PUT method described in the last lesson updates the whole record. There may be a scenario when only one or two fields needs to be updated. In that case, sending the whole record does not make sense. The HTTP PATCH method is used for partial updates.
Spring provides the ReflectionUtils class for handling reflection and working with the Reflection API.
The ReflectionUtils class has a findField method to identify the field of an object using a String name. The findField method takes two arguments, the class having the field and the name of the field which in our case is contained in the variable key.

@Modifying
@Query("update Player p set p.titles = :titles where p.id = :id")
void updateTitles(@Param("id") int id, @Param("titles") int titles);
This query must be used with the @Modifying annotation to execute the UPDATE query. @Param binds the method parameters to the query. 


The difference lies in the way both methods respond when the entity to be deleted is not found. The deleteById method throws the EmptyResultDataAccessException while delete throws a NoSuchElementException.

Exception Handling I
When the client sends a request to fetch, update or delete a player record not found in the database, an internal server error occurs. The information contained in the response is verbose and of interest to developers only


Custom error response class#
1.	In order to send a custom response to the client, we will create a class with fields like status code, error message, path/URI, and timestamp. An object of this class will be created when an exception occurs and sent back to the client as the response. Jackson will automatically handle data binding and send this object as a JSON response.



2.	When the REST service receives a bad request, we want it to throw an exception of our custom type. Since the exception is thrown when the player is not found , we will call the class PlayerNotFoundException. This class extends the RunTimeException class.

throw exception#
3.	Now that we have defined a custom exception class, we are in a position to throw exceptions of this class



@ControllerAdvice:
A best practice in exception handling is to have centralized exception handlers that can be used by all controllers in the REST API. Since exception handling is a cross cutting concern, Spring provides the @ControllerAdvice annotation. This annotation intercepts requests going to the controller and responses coming from controllers.


to use it as an interceptor of exceptions thrown by methods annotated with @RequestMapping or any of its shortcut annotations. The exception handling logic is contained in the global exception handler which handles all exceptions 


@ControllerAdvice annotation can act as a global exception handler

we need a mechanism to catch exceptions. We will write a handler method to catch the exception thrown by the methods.


. This handler method will create an appropriate response for the client.


The input to this method is the type of the exception it will handle as well as the HttpServletRequest object


The method returns a ResponseEntity object containing the HTTP response when the exception occurs


An HTTP response message has three parts: response line, header and body, as discussed 

The @ExceptonHandler annotation on a method, marks it as a method that will handle exceptions. Spring automatically checks all methods marked with this annotation when an exception is thrown. If it finds a method whose input type matches the exception thrown, the method will be executed.


@ExceptonHandler
public ResponseEntity<PlayerErrorResponse> playerNotFoundHandler (PlayerNotFoundException exception, HttpServletRequest req) {

}




What is AOP?#
Aspect Oriented Programming (AOP) is the best approach for implementing cross-cutting concerns. Applications are divided into layers like web, business, data, etc. Each layer works independently. There are some concerns that are common across layers. These include security, logging, transaction management, auditing, error handling, performance tracking

These concerns are present in all the layers and are thus called cross-cutting concerns

AOP provides an easy way to add concerns like printing logs or tracking performance of methods across layers


Using the OOP approach, we can call the logger from these methods. The problem with such an approach is that in future, if the logs are not needed anymore, or if they are needed for another group of methods, we will have to make changes to the source code. 




By following the AOP approach, such changes are easy to maintain. Instead of changing the source code, concerns are implemented separately. Thus, any cross-cutting concern can be added and removed without recompiling the complete code by only changing the config files. The logging functionality can be defined separately and applied to any method belonging to any layer easily.




Difference between OOP and AOP:
spring-aop#
spring-aop is a popular implementation of AOP provided by Spring. It is not as powerful as AspectJ. spring-aop can be used to intercept any calls to the beans managed by Spring. Once method calls are intercepted, cross-cutting concerns can be applied before, after, or around the method logic.



CommandLineRunner is used when we want to execute some code right after the context is loaded and as soon as the startup completes.


Aspect#
An aspect is a Java class that implements cross-cutting concerns. The @Aspect annotation is used to define a class as an aspect. An aspect is a combination of the kinds of methods to intercept and what to do after intercepting them.
Aspects can define functionality for any concern like logging, performance management, or transaction management that cuts across multiple application layers.
Pointcut#
Pointcuts are expressions that determine which method calls will be intercepted. These expressions determine whether an advice needs to be executed or not. Pointcuts are defined following a particular syntax.
Pointcuts should be carefully defined, as they determine how many calls will be intercepted.






Advice#
The tasks performed after intercepting a method call are called advices. It is the logic of the methods in a class marked with @Aspect. Advices are basically the methods that get executed when a method calls meets a pointcut. These methods can get executed before, around the time of, or after the execution of the intercepted method call. There are different advice types



Joinpoint#
All method calls that are intercepted are joinpoints. It is a point in the program execution where an aspect can be plugged in. It contains the name of the intercepted method call. The following figure shows the big picture of how AOP works:
Pointcut maps to a joinpoint where an aspect can be executed during program execution
Weaving#
The process of implementing AOP around method calls is called weaving. Weaving links an aspect with objects in the application to create an advised object. The aspect is called at the right moment. For example, if we are tracking the execution time of some methods in our application, the weaving process will be like this:
Implementing aspects around business logic
Weaver#
The framework that ensures that an aspect is invoked at the right time is called a weaver.

we will define an aspect to intercept all the calls to the business layer and log their output. We will create a number of aspects and place all of them in a separate package.
When we intercept method calls, we have the option to perform tasks before the method is executed as well as afterwards. To define an aspect for a cross-cutting concern, we will perform the following steps:
•	Define aspect class.
•	Write methods containing the advice to be executed when method calls are intercepted.
•	Write pointcut expressions for intercepting method calls.


Aspect#
1.	Suppose we want to intercept method calls to check if the user has access before the method gets executed. Access check is a cross-cutting concern and instead of implementing it in every method, we can write it as an aspect.
We will create a class called AccessCheckAspect and place it in the aspect package. To establish that this is a configuration class, we will use the @Configuration annotation. We will also add the @Aspect annotation to establish that this class is related to AOP.
@Aspect
@Configuration
public class AccessCheckAspect {

}
Advice#
2.	The next step is to define a method that contains the logic of the steps that need to be carried out when a method call gets intercepted. We will create a method called userAccess and print a message as follows:
@Aspect
@Configuration
public class AccessCheckAspect {
    private Logger logger = LoggerFactory.getLogger(this.getClass());

    public void userAccess(JoinPoint joinPoint) {
        logger.info("Intercepted method call");
    }
}
Pointcut expression#
3.	User access needs to be checked before a method gets executed. We need the @Before annotation on our method. It ensures that the advice is run before the method is executed.
@Before needs an argument which specifies the method calls that will be intercepted. This is called the pointcut. Pointcuts are defined in the following format:
execution(* PACKAGE.*.*(..))
The pointcut expression starts with a key word called a designator, which tells Spring AOP what to match. execution is the primary designator which matches method execution joinpoints.
•	The first * in the expression corresponds to the return type. * means any return type.
•	Then comes the package name followed by class and method names.
•	The first * after package means any class and the second * means any method. Instead of *, we could specify the class name and method name to make the pointcut expression specific.
•	Lastly, parentheses correspond to arguments. (…) means any kind of argument.
Suppose we want to intercept calls to methods belonging to the business package. The pointcut expression, in this case, will be:
@Before("execution(* io.datajek.springaop.movierecommenderaop.business.*.*(..))")




If we use this pointcut expression and run the application, the message in the method will be printed twice, indicating that two method calls have been intercepted.
The userAccess method is invoked before the actual method. This method contains the logic for checking user access, which is not shown.
Joinpoint#
4.	To find out which method calls have been intercepted, we will use a join point as an argument to the method. The joinpoint contains the name of the method that is intercepted. We can use the joinpoint to print the name of the method as follows:
@Before("execution(* io.datajek.springaop.movierecommenderaop.business.*.*(..))")
public void userAccess(JoinPoint joinPoint) {
    logger.info("Intercepted call before execution: {}", joinPoint);
}



@Aspect
@Configuration
public class AccessCheckAspect {

	private Logger logger = LoggerFactory.getLogger(this.getClass());
	
	@Before("execution(* io.datajek.springaop.movierecommenderaop.business.*.*(..))")
	public void before(JoinPoint joinPoint) {
		//	logger.info("Intercepted method call");
		logger.info("Intercepted call before execution of: {}", joinPoint);
		
		//access check logic		
	}
}



Pointcut Expressions
The way pointcuts are defined is important because it decides the method calls that will be intercepted. If we have two packages, we can define which method calls will be intercepted.



Intercepting calls using return type#
3.	Say we want to intercept calls to all methods that return a String value. This can be done by specifying String as the return type in the pointcut expression as follows:
@Before("execution(String io.datajek.springaop.movierecommenderaop..*.*(..))")


Intercepting calls to a specific method#
4.	If we want to intercept calls to all methods that have the word Filtering in it, we will use the following pointcut expression:
@Before("execution(String io.datajek.springaop.movierecommenderaop..*.*Filtering(..))")
The wildcard * used in place of the method name will match all methods that have the word Filtering in it. 



Intercepting calls with specific method arguments#
5.	Consider the following pointcut expression:
@Before("execution(* io.datajek.springaop.movierecommenderaop..*.*(String))")
This pointcut will match method calls having one parameter of String type. We can modify this expression to match all method calls with String as the first argument 



@Before("execution(*io.datajek.springaop.movierecommenderaop..*.*(String,..))")



Combining pointcut expressions#
6.	The && , || and ! symbols can be used to combine different pointcut expressions.
@Before("execution(* io.datajek.springaop.movierecommenderaop..*.*Filtering(..)) || execution(String io.datajek.springaop.movierecommenderaop..*.*(..))")





This pointcut expression will match method calls that have the word Filtering in them as well as those that return a String. In all, four methods will be intercepted matching either of the two conditions.




After Aspect
Logging is a cross-cutting concern for which aspects can be created. In this lesson, we will create another aspect that will log the values returned after the methods have been executed.
1.	We will create an aspect called LoggingAspect by creating a Java class and mark it with @Aspect and @Configuration annotations.
@Aspect
@Configuration
public class LoggingAspect {

}



@AfterReturning#
2.	The LoggingAspect class will have a method LogAfterExecution, which will print a message if the method is successfully executed.
To tell spring-aop that this method needs to be called after the intercepted method call is executed, we will use the @AfterReturning annotation.
@AfterReturning("execution(* io.datajek.springaop.movierecommenderaop.data.*.*(..))")
public void LogAfterExecution(JoinPoint joinPoint) {
    logger.info("Method {} complete", joinPoint);
}
We can get the return values of the method here by using the returning tag. Now that pointcut is not the only argument in the @AfterReturning annotation, we will use tags to differentiate arguments as follows:
@AfterReturning(
 value = "execution(* io.datajek.springaop.movierecommenderaop.business.*.*(..))",
 returning = "result")
public void LogAfterExecution(JoinPoint joinPoint, Object result) {
    logger.info("Method {} returned with: {}", joinPoint, result);
}
value contains the pointcut expression and returning contains the value that is returned by the executing method, which is stored in result and passed to the LogAfterExecution method. Note that result is of type Object because different methods will have different return types.
We can use result to log the return value of all intercepted methods. If the application is run, two methods from the business layer are intercepted and the return values are also displayed.
@AfterThrowing#
3.	To intercept an exception, another annotation, @AfterThrowing, is used. We can get the result of the exception using the throwing tag.
We will use this pointcut on a method called LogAfterException as follows:
@AfterThrowing(
 value = "execution(* io.datajek.springaop.movierecommenderaop.business.*.*(..))",
 throwing = "exception")
public void LogAfterException(JoinPoint joinPoint, Object exception) {
    logger.info("Method {} returned with: {}", joinPoint, exception);
}
This advice will be executed in case there is an exception in any method call from the business layer.
@After#
4.	The @After annotation is a generic annotation that is used in both scenarios, whether the method execution is successful or results in an exception. The method LogAfterMethod demonstrates the use of this annotation.
@After("execution(* io.datajek.springaop.movierecommenderaop.business.*.*(..))")
public void LogAfterMethod(JoinPoint joinPoint) {
    logger.info("After method call {}", joinPoint);
}
Since @After is a generic annotation, if the application is run, this method also gets executed alongside the LogAfterExecution method marked with the @AfterReturning annotation.




Around Aspect
So far, we have seen examples of aspects that are executed before and after the intercepted method calls. This lesson looks at another type of aspect, the around aspect, which is executed around the intercepted method call. This kind of aspect is useful if we want to perform a task before the intercepted method starts execution and after the method has returned.
A good example of an around aspect is measuring the time taken by the method call to execute. We can note the time when the method call is intercepted, then allow the intercepted method to execute, and note the time after the method returns. Instead of having two separate annotations, @Before and @After, we can accomplish this task using the more advanced @Around annotation.




1.	We will create a class called ExecutionTimeAspect. To mark it as an aspect and a configuration, we will use the @Aspect and @Configuration annotations as follows:
@Aspect
@Configuration
public class ExecutionTimeAspect {

}
2.	In the ExecutionTimeAspect class, we will create a method called calculateExecutionTime. The parameter type of this method will be ProceedingJoinPoint instead of JoinPoint, which we have used with methods marked with @Before and @After annotations. ProceedingJoinPoint allows the continuation of the execution. This method will return an Object that contains the values returned after the execution of the intercepted method call. The proceed method of ProceedingJoinPoint should either be surrounded by a Try Catch block or should include a throws declaration with the method definition.




public Object calculateExecutionTime(ProceedingJoinPoint joinPoint) throws Throwable {
    //note start time
    long startTime = System.currentTimeMillis();
        
    //allow method call to execute
    Object returnValue = joinPoint.proceed();
        
    //time taken = end time - start time
    long timeTaken = System.currentTimeMillis() - startTime;
        
    logger.info("Time taken by {} to complete execution is: {}", joinPoint, timeTaken);
    return returnValue;
}



3.	Now, we will use the @Around annotation to define a pointcut for method calls for which we want the execution time to be tracked. If we want the time of all methods to be tracked, the following pointcut expression will be used:
@Around("execution(* io.datajek.springaop.movierecommenderaop..*.*(..))")




@Aspect
@Configuration
public class ExecutionTimeAspect {

	private Logger logger = LoggerFactory.getLogger(this.getClass());

	@Around("execution(* io.datajek.springaop.movierecommenderaop..*.*(..))")
	public Object calculateExecutionTime(ProceedingJoinPoint joinPoint) throws Throwable {
		//note start time
		long startTime = System.currentTimeMillis();
		//allow method call to execute
		Object returnValue = joinPoint.proceed();
		//time taken = end time - start time
		long timeTaken = System.currentTimeMillis() - startTime;
		
		logger.info("Time taken by {} to complete execution is: {}", joinPoint, timeTaken);
		return returnValue;
	}
}



JoinPoint Configuration File
In the last few lessons, we have created aspects to intercept method calls and perform tasks before, after, or around the execution. We have been repeating the same pointcuts over and over again. In an application with a large number of aspects, this can become cumbersome.
A best practice related to AOP is to have a separate configuration file that defines all the pointcuts. This way, all the pointcut definitions will be in one place. Hence they will be easy to manage. We can then use the definitions in any aspect.
For a specific layer#
1.	We will create a class called JoinPointConfig and define pointcuts using the @pointcut annotation. This annotation will be used on an empty method as follows:
@Pointcut("execution(* io.datajek.springaop.movierecommenderaop.data.*.*(..))")
public void dataLayerPointcut() {}
Now, we can use the dataLayerPointcut method by providing its fully qualified name wherever we want to intercept execution of methods in the data layer.
2.	Previously, we had been using pointcuts as follows:
@AfterReturning("execution(* io.datajek.springaop.movierecommenderaop.data.*.*(..))")
public void logAfterExecution(JoinPoint joinPoint) {
    //...
Now, we will use the method that defines this pointcut in the configuration file as follows:
1
2
3
4
@AfterReturning("io.datajek.springaop.movierecommenderaop.aspect.JoinPointConfig.dataLayerPointcut()")  
public void logAfterExecution(JoinPoint joinPoint) {
    //...
}
3.	In the same manner, we can create a pointcut configuration for intercepting method calls in the business layer as follows:
1
2
@Pointcut("execution(* io.datajek.springaop.movierecommenderaop.business.*.*(..))")
   public void businessLayerPointcut() {}
The fully qualified name of businessLayerPointcut can be used in place of the pointcut definition in AccessCheckAspect without affecting the output as follows:
@Before("io.datajek.springaop.movierecommenderaop.aspect.JoinPointConfig.businessLayerPointcut()")
public void before(JoinPoint joinPoint) {
 //. . .
}
For multiple layers#
4.	We can also combine pointcuts using the AND (&&), (OR) ||, and (NOT) ! operators. The method allLayerPointcut will intercept calls belonging to either the business layer or the data layer.
1
2
3
@Pointcut("io.datajek.springaop.movierecommenderaop.aspect.JoinPointConfig.dataLayerPointcut() || "
            + "io.datajek.springaop.movierecommenderaop.aspect.JoinPointConfig.businessLayerPointcut()")
public void allLayersPointcut() {}
When this pointcut is used in AccessCheckAspect, four method calls are intercepted.
For a bean#
5.	We can also define a pointcut to intercept calls belonging to a particular bean. Say we want to log the execution of all methods belonging to beans that have the word Movie in their name. We can define a pointcut as follows:
@Pointcut("bean(movie*)")
    public void movieBeanPointcut() {}
When this pointcut is used in AccessCheckAspect, it will intercept calls from the Movie and MovieRecommenderAopApplication beans.
package io.datajek.springaop.movierecommenderaop.aspect;

import org.aspectj.lang.annotation.Pointcut;

public class JoinPointConfig {

	@Pointcut("execution(* io.datajek.springaop.movierecommenderaop.data.*.*(..))")
	public void dataLayerPointcut() {}
	
	@Pointcut("execution(* io.datajek.springaop.movierecommenderaop.business.*.*(..))")
	public void businessLayerPointcut() {}
	
	//to intercept method calls for both layers:
	@Pointcut("io.datajek.springaop.movierecommenderaop.aspect.JoinPointConfig.dataLayerPointcut() || "
			+ "io.datajek.springaop.movierecommenderaop.aspect.JoinPointConfig.businessLayerPointcut()")
	public void allLayersPointcut() {}
	
	//for a particular bean
	@Pointcut("bean(movie*)")
	public void movieBeanPointcut() {}
}

Defining a Custom Annotation for Aspects

Pg: 130

We have seen the example of an aspect used to track the execution time of a method which intercepted calls to a particular layer. Another approach could be to define a custom annotation on any method for which we want to track the execution time. spring-aop allows us to create our own annotations and define aspects to implement them.
1.	Suppose we want to call our annotation @MeasureTime. We will create an annotation, MeasureTime, in the same folder as the other aspects. This creates an interface:
package io.datajek.springaop.movierecommenderaop.aspect;

public @interface MeasureTime {

}
2.	We will restrict the use of this annotation to methods only. This can be achieved using the @Target annotation, with ElementType set to METHOD. Other options include class, package, field, etc.
@Target(ElementType.METHOD)
We would also like the annotation information to be available at runtime. We will use the @Retention annotation to define a retention policy as follows:
@Retention(RetentionPolicy.RUNTIME)
3.	Now that we have defined our annotation, we can add it to the JoinPointConfig file and create a pointcut as follows:
public void measureTimeAnnotation() {}
We can now use this pointcut to calculate the execution time of only chosen methods. Previously, the ExecutionTimeAspect looked like this:
public class ExecutionTimeAspect {
    private Logger logger = LoggerFactory.getLogger(this.getClass());

 @Around("io.datajek.springaop.movierecommenderaop.aspect.JoinPointConfig.businessLayerPointcut()")
    public Object calculateExecutionTime(ProceedingJoinPoint joinPoint) throws Throwable {
    //. . .
    }
}
Instead of tracking the time of business layer methods, we will intercept methods using the @MeasureTime annotation:
public class ExecutionTimeAspect {
    private Logger logger = LoggerFactory.getLogger(this.getClass());
 @Around("io.datajek.springaop.movierecommenderaop.aspect.JoinPointConfig.measureTimeAnnotation()")
public Object calculateExecutionTime(ProceedingJoinPoint joinPoint) throws Throwable {
        //. . .
    }
}
Since we haven’t used the annotation anywhere in the code yet, no call will be intercepted. Suppose we want to track the time for the contentBasedFiltering method of the FilteringTechnique1 class and the getMovieDetails method of the Movie class. We will use our custom annotation on these methods:
@MeasureTime
public String contentBasedFiltering() {
    String movieDetails = movie.getMovieDetails();
    return movieDetails;
}
@MeasureTime
public String getMovieDetails() {
    return "movie details";     
}
If the application is run after adding @MeasureTime, calls to both these methods will be intercepted and the execution time will be measured.





Spring MVC Architecture
Spring MVC is a framework for building web applications in Java which is based on the MVC design pattern. It uses the features of the core spring framework like Inversion of Control (IoC) and dependency injection.
Spring MVC request flow#
In a nutshell, a request coming from the client is handled by the Spring MVC front controller which delegates the request to another controller. The controller creates a model and based on the user request, populates the model. Then it returns the model to the front controller. Now, the front controller passes this model to the view template which takes the data and renders the response to the client.
MVC architecture has a front controller that manages all the other controllers. The developer creates the controllers for the application and Spring MVC provides the front controller. The job of the front controller is to handle all requests coming from the client.


. It is the job of the front controller to call another controller based on the request that it receives.



Dispatcher servlet#
The front controller is called the DispatcherServlet. In order to know which controller to call, the dispatcher servlet needs a configuration file which contains information about where the controllers are placed. The @Controller annotation is used on all controllers and they are placed in the same package.
A request from the client goes to the web.xml as usual. In MVC architecture, web.xml forwards it to the dispatcher servlet. The dispatcher servlet checks its configuration file to find out which controller to invoke.
After the controller is executed, it sends two things back to the dispatcher servlet; the data or result (model) and the name of the page (view) to show to the client. The dispatcher servlet calls the view resolver to find the appropriate page, populates the page with the results and shows it to the client.



the dispatcher servlet manages everything in MVC architecture. The client need not know about the other controllers in the application. It only interacts with the dispatcher servlet.




All incoming requests to a Spring MVC application are handled by the front controller called the DispatcherServlet. This front controller is part of the Spring JAR files and the developer is not required to implement it.
The front controller delegates an incoming request to other components of the application. The controllers contain the business logic, model contains the data, and views are the pages that render that data. The controller class populates the model and sends it to the front controller. The front controller forwards it to the view resolver which resolves the view that renders the model to the client.


The front controller maps the incoming request to a controller. Controller contains the business logic of the application. The function of the controller is to handle a user request. The incoming request may be handled in different ways like reading form data, processing it in some way, storing data in a database, or retrieving data from a web service etc. The controller places the data in the model which, simply put, is a container for the data. The controller returns the model (containing data) back to the front controller.


•	The dispatcher servlet is part of the core Spring framework and is defined in org.springframework.web.servlet.DispatcherServlet


4.	Every incoming request in Spring MVC application is handled by the dispatcher servlet. 


The dispatcher servlet config file will contain the following:
•	Component scanning support
•	Data validation and type conversion support
•	View resolver configuration



The @ResponseBody annotation tells the dispatcher servlet that the response coming back is not the name of a view. Rather, it is the response that we want to send back to the user. Without using this annotation, if we run the application and type http://localhost:8080/spring/, we will get a 404 error which indicates that the page is not found because the dispatcher servlet by default searches for a URL mapping. 



we created a bean of InternalResourceViewResolver class in the player-servlet.xml file, which had information to append a String as prefix and suffix to construct the complete location of the view


JUnit:
. Testing is done at different levels and in different ways. Testing an application after deployment is called screen testing or system testing. Testing a specific method or a class is called unit testing. It usually involves writing tests for each method of a class. Unit tests can also be written for a group of methods or to test the whole class.


Junit3/Junit4 -> Vintage
Junit5 -> Jupiter
Other tests-> Third party

To enable JUnit, we need the JUnit engine and the Jupiter API to create tests. When creating a Spring Boot project, JUnit is already included as a dependency.


. test scope means that this dependency will not be included in the final build.

JUnit’s way of reporting the status of the test is by using one of the assert methods.

JUnit Test Lifecycle Annotations:

For example, some initialization code needs to be run before each test, and some cleanup code needs to be run after each test. If we have multiple tests, there might be some code that we want to initialize before any of the tests run. Similarly, there might be some teardown code that we want to run after each test has run.
JUnit provides annotations that can be used on each of these lifecycle hooks. These annotations are @BeforeAll, @AfterAll, @BeforeEach, and @AfterEach


Mockito Annotations
There are some Mockito annotations that help minimize the code for creating and injecting mocks.
@Mock
@InjectMocks

We need to use the @ExtendWith annotation and pass MockitoExtension.class as an argument to integrate Mockito with the JUnit 5 extension model. MockitoExtension enables the evaluation of the @Mock annotations to initialize mocks, which was previously done using the Mockito.mock method.


When to use @SpringBootTest#
The value of @SpringBootTest is in testing the whole application because it loads the complete context like in the production environment. For a unit test, there is no need to load the complete context. In fact, loading the entire context will have an impact on performance since unit tests should only take a few milliseconds to run.


@ContextConfiguration
. To load the context using Spring, we will use @ContextConfiguration. This loads only part of the configuration and is thus more suitable for unit testing.



After the context has been defined, we need to run it. This is done by using the @ExtendWith annotation with SpringExtension.class as its argument. SpringExtension provides a bridge between Spring and JUnit.



Is Spring 5 compatible with older versions of Java?#
No, because Spring 5 requires a minimum of Java 8. It is not compatible with older versions of Java as the code base of Spring has been revamped to take advantage of the features of Java 8.




Spring framework uses a number of design patterns:
•	Factory Pattern: BeanFactory and ApplicationContext classes
•	Singleton Pattern: Singleton-scoped beans
•	Prototype Pattern: Prototype-scoped beans
•	Proxy Pattern: Spring Aspect Oriented Programming support
•	Template Method Pattern: JdbcTemplate, JmsTemplate, JpaTemplate etc.
•	Data Access Object Pattern: Spring DAO support
•	Model View Controller Pattern: Spring MVC
•	Front Controller Pattern: DispatcherServlet in Spring MVC
•	View Helper Pattern: custom JSP tags separate code from presentation in views.
•	Adapter Pattern: JMS adapters and JDBC adapters in Spring Integration




some of the best practices for Spring Framework?#
•	Only use the modules that are needed by the application and remove any extra modules that get added when Spring Tools Suite is used.
•	Use annotation according to the application layer. @Service for business logic and @Repository for data layer.
•	Create an external property file to configure property values.
•	Use Spring Initializer for starting new Spring Boot projects to get a tested and approved set of dependencies and to save time.
•	Use Controller classes to delegate business logic to the service layer.
•	Use a logging framework instead of doing it manually using System.out.println().



some standard Spring events.#
Events provide a way of communication between loosely coupled components. ApplicationContext in Spring publishes certain events during the lifecycle of a Spring application.
Standard Spring events include:
•	ContextStartedEvent: triggered when the context is started.
•	ContextRefreshedEvent: triggered when the context is either initialized or refreshed using the refresh() method.
•	ContextStoppedEvent: triggered when the context is stopped using the stop() method.
•	ContextClosedEvent: triggered when the close() method is called on the ApplicationContext.
•	RequestHandledEvent: triggered to let all beans know that an HTTP request has been handled.



How does Spring 5 make use of JDK 9 modularity?#
Java 9 introduces modules which are a reusable collection of related packages, resources (XML files) and a module descriptor that specifies name, dependencies, and packages that are available for use.
A Spring 5 project can be built around this concept. Consider the following example in which we have a ModuleExample class in the io.datajek.modularitydemo package.
package io.datajek.jdkmodularity;
public class ModuleExample{
   public String displayMessage(){
       return "Spring 5 with JDK 9 Modularity";
   }
}
To make this package available to another package, we can make it part of a module. This is done using the module keyword. The export keyword is used to specify the package whose public methods are available to other modules.
module io.datajek.modularityexample {
   export io.datajek.jdkmodularity;
}
This module can be used in any other java project by using the require keyword. This defines a dependency relationship where io.datajek.modularityexample.demo depends on io.datajek.modularityexample.
module io.datajek.modularityexample.demo {
   requires io.datajek.modularityexample;
}
The ModuleExample class and its public methods can now be accessed in the new module as follows:
public class ModuleExampleExplained {
   public static void main(String[] args){
       ModuleExample moduleExample = new ModuleExample();
       moduleExample.displayMessage();
   }
}





IoC and Dependency Injection
Inversion of Control (IoC)#
What is Inversion of Control (IoC)?#
Suppose, class A is dependent on class B. In case of tight coupling, class A is responsible for creating an object of class B. In case of loose coupling, the framework takes the responsibility of creating and populating the dependency. The control of creating dependency shifts from the class to the framework. This is called Inversion of Control (IoC).
What are the advantages of Inversion of Control?#
•	IoC minimizes the amount of code in the application since the framework is now responsible for creating and wiring the dependencies.
•	Inversion of Control leads to loose coupling where it becomes easy to change implementations of an interface.
•	It leads to better testability as mock objects can be created for the application.
•	IoC supports eager instantiation as well as lazy loading.
What is the responsibility of an IoC container?#
An IoC container performs the following tasks:
•	It instantiates the application class.
•	It identifies the beans along with their dependencies and wires the dependencies.
•	It manages the lifecycle of the beans from the time they are created till the time they are destroyed.
The IoC container uses the configuration metadata, in the form of an XML file or Java annotations, which contains instructions about the objects and their dependencies.
Describe the two types of IoC container.#
The two types of IoC container are BeanFactory and ApplicationContext. These are interfaces, with various implementations, that act as the IoC container.
BeanFactory provides basic functionality of an IoC container while ApplicationContext adds extra functionality like AOP, message resource handling for internationalization and WebApplicationContext for web applications.
Spring recommends using ApplicationContext unless the resources are limited, like for example on a mobile device or for applet based applications.
Give an example of the BeanFactory implementation.#
The most commonly used implementation of BeanFactory is the XmlBeanFactory class. This container reads the metadata from an XML config file to create a fully configured application.
What is ApplicationContext?#
ApplicationContext is a type of IoC container. It extends the BeanFactory interface.
Similar to the BeanFactory, the ApplicationContext can load bean definitions, wire beans together and return beans upon request. Additional features of ApplicationContext that are not part of the BeanFactory are support for AOP and internationalization, publishing events, and application layer specific contexts like WebApplicationContext.
Give examples of the ApplicationContext implementations.#
Commonly used implementations of ApplicationContext are:
•	ClassPathApplicationXmlContext: reads the configuration from an XML file for standalone java applications.
•	AnnotationConfigApplicationContext: uses annotation based configuration for standalone java applications.
•	AnnotationConfigWebApplicationContext and WebXmlApplicationContext: for web applications.
What is the difference between BeanFactory and ApplicationContext?#
The default implementation of BeanFactory uses lazy initialization. It instantiates beans when the getBean() method is called. ApplicationContext extends the BeanFactory interface but the default implementation uses eager initialization. The beans are instantiated when the application starts. However, this behavior can be overridden.
BeanFactory does not support annotation based dependency injection. This feature was included in ApplicationContext.
How is ApplicationContext configured in Spring?#
There are multiple ways to configure application context:
•	Application context can be configured using XML. The context can be created using ClassPathXmlApplicationContext, FileSystemXmlApplicationContext, or GenericXmlApplicationContext class which looks for XML file defining the configuration.
•	Annotations can also be used to automatically register classes in the application context. The @Component annotation (along with @Controller, @Service and @Repository annotations) are used on classes and the AnnotationConfigApplicationContext class is used to create the application context.
•	Java configuration using the @Configuration annotation on classes and @Bean annotation on methods is another way to configure the application context. The AnnotationConfigApplicationContext class is used to create the context by scanning the annotations.



191

•	IoC supports eager instantiation as well as lazy loading


An IoC container performs the following tasks:
•	It instantiates the application class.
•	It identifies the beans along with their dependencies and wires the dependencies.
•	It manages the lifecycle of the beans from the time they are created till the time they are destroyed.


BeanFactory provides basic functionality of an IoC container while ApplicationContext adds extra functionality like AOP, message resource handling for internationalization and WebApplicationContext for web applications.
Spring recommends using ApplicationContext unless the resources are limited

The most commonly used implementation of BeanFactory is the XmlBeanFactory class. This container reads the metadata from an XML config file to create a fully configured application


ApplicationContext is a type of IoC container. It extends the BeanFactory interface.
Similar to the BeanFactory, the ApplicationContext can load bean definitions, wire beans together and return beans upon request. Additional features of ApplicationContext that are not part of the BeanFactory are support for AOP and internationalization, publishing events, and application layer specific contexts like WebApplicationContext.




Commonly used implementations of ApplicationContext are:
•	ClassPathApplicationXmlContext: reads the configuration from an XML file for standalone java applications.
•	AnnotationConfigApplicationContext: uses annotation based configuration for standalone java applications.
•	AnnotationConfigWebApplicationContext and WebXmlApplicationContext



the difference between BeanFactory and ApplicationContext?#
The default implementation of BeanFactory uses lazy initialization. It instantiates beans when the getBean() method is called. ApplicationContext extends the BeanFactory interface but the default implementation uses eager initialization. The beans are instantiated when the application starts.


WebApplicationContext?#
WebApplicationContext interface extends ApplicationContext interface. It provides configuration for web applications.
WebApplicationContext defines request, session and global application scopes in addition to the singleton and prototype scopes in ApplicationContext.


What happens if the context is not closed?#
Not closing the context leads to resource leak. The close() method destroys all beans, releases the locks and closes the bean factory. Similarly, using a try-with-resources block also ensures that each resource is closed when the block exits.



What are the types of dependency injection?#
A dependency can be injected in several ways:
•	Field injection
•	Setter injection
•	Constructor injection



What is the difference between constructor and setter injection?#
•	Constructor injection is not partial while setter injection offers partial dependency injection. If an object has 5 fields, it is not possible to pass just 1 in a 5 argument constructor.
•	Constructor injection does not override setter, whereas setter injection overrides constructor if both are defined. The IoC container by default chooses setter injection.
•	Constructor injection works well if the number of properties is large, whereas setter injection would make the code longer in such a scenario.



•	Setter injection is flexible because it is possible to change the value of the property without creating a new bean instance. In case of constructor injection, a new bean is needed if a property is modified.


The documentation for older versions of Spring suggested that constructor injection be used for all mandatory dependencies while setter injection for optional dependencies. However the @Required annotation on a setter method can be used to make it a mandatory dependency.


What is method injection?#
Any method can be used for setting the dependency if the @Autowired annotation is used on it. This is referred to as method injection. The method can have any name. As long as it has the @Autowired annotation, Spring will find a matching dependency to inject.



What is a circular dependency and how should it be resolved?#
When beanA has a dependency on beanB and benB has a dependency on beanA, it results in a circular dependency. In this case both beans try to inject each other via constructor and Spring throws BeanCurrentlyInCreationException.




Spring creates beans in order in which they are needed. If a bean has a dependency, then the dependency is created first and then injected to complete the creation of the bean. In case of circular dependency, spring cannot decide which bean to create first.
Circular dependency issue arises when using constructor injection because the beans are created when the context is loaded. If using setter or field injection, the beans are created but their dependencies are injected only when they are needed. Thus the circular dependency issue can be avoided.
When using constructor injection, @Lazy annotation can be used. This tells spring that when initializing the bean, inject a proxy. The bean is fully created only when it is needed.




    @Autowired
    public ClassA(@Lazy ClassB classB) {
        this.classB = classB;
    }

a Spring bean is a Java object. When Java objects are created by the Spring container, they are referred to as Spring Beans.


Beans are managed by the Spring container using the configuration metadata in the form of XML or Java annotations. The container instantiates, assembles and manages the lifecycle of a bean. For example, the @Component annotation on a class tells Spring framework that it has to manage the lifecycle of the objects of that class



What is the lifecycle of a Spring Bean?#
Spring container instantiates a bean and initializes it. It also injects the required dependencies. When the context is destroyed, all the initialized beans are also destroyed.
Spring provides post initialization and pre destruction methods for custom tasks. These methods can be invoked using XML config file or Java annotations.
What are custom bean lifecycle methods?#
During the lifecycle of the bean, Spring allows the developer to add custom code during bean initialization and bean destruction. This can include code for custom business logic at initialization or destruction as well as setting up and cleaning up resources like a database connection or a file etc.



What are some features of custom init and destroy methods?#
•	Custom methods for initialization and destruction can have any name.
•	They can have any access modifier; private, public, or protected.
•	They can have any return type, but since the return value cannot be captured, void is mostly used as the return type.
•	They cannot have any input arguments.




What information does the bean definition contain?#
Bean definition contains information for the container in the form of configuration metadata. Bean definition contains the following information:
•	How the bean is created.
•	Lifecycle details of the bean.
•	Dependencies of the bean.




Are Spring beans same as JavaBeans?#
JavaBeans are Java classes that follow certain coding conventions. They have a public no-arg constructor, have private properties and allow access to properties using getter and setter methods and implement the java.io.Serializable interface.
Spring beans are objects whose lifecycle is managed by the Spring container. They do not follow the rigorous requirements of JavaBeans.
Spring beans are often the same as JavaBeans but they don’t have to be. Spring beans can have constructor with arguments and may not implement the java.io.Serializable interface.




How are beans created?#
Spring framework creates beans in an order. When Spring framework encounters a bean definition in XML file or through an annotation, it checks if the class is dependent on any other class. Suppose class A has a dependency on class B. In this case, Spring will create the object of class B. Once the dependency has been created, the bean for class A can be created by injecting the bean of class B in class A.



pg: 197
What does the @Bean annotation do?




What does the @Bean annotation do?#
The @Bean annotation is used on a method to indicate that the method returns a bean to be managed by Spring. The name of the method indicates the bean id. This annotation is used in classes marked with @Configuration annotation.
The @Bean annotation provides the same functionality as the &ltbean> tag in XML configuration.


Both @Bean and @Component annotations create beans. What is the difference between the two?#
Some differences between the two annotations are:
•	@Component enables Spring to auto-detect and auto-configure beans while @Bean is used to explicitly declare a bean rather than letting Spring auto-detect it.
•	@Component is a class level annotation while @Bean is a method level annotation.
•	Since @Component annotation is used on a class, it keeps the bean definition and class declarations together while @Bean decouples them.




What are the different scopes of a bean?#
In Spring 5, six scopes have been defined. They are:
•	Singleton. Only one instance of the bean per IoC container is created.
•	Prototype. A new instance of the bean is created every time.
•	Session. One bean is created for every Http session.
•	Request. One bean is created per Http request.
•	Application. One bean is created per ServletContext.
•	Websocket. One bean is created per WebSocket.
The singleton and prototype scopes can be used in any application while the last four scopes are only available for a web application.



When are singleton and prototype scopes used?#
Singleton scope is used for beans which are stateless whereas prototype scope is for beans in which we need to maintain a state.



The IoC container handles both types differently. It manages the entire lifecycle of singleton beans but does not do so in the case of prototype beans. The developer is responsible for destroying the prototype beans.
How is bean scope defined?#
The @Scope annotation is used to set the scope of a bean. 


Is Singleton scope in Spring same as the Singleton design pattern?#
According to the Singleton design pattern, there can be one bean per Java class. In Spring, singleton scope means one bean per bean id per Spring container (ApplicationContext).


Are Singleton beans thread safe?#
No, Singleton beans are not thread safe. Thread safety depends upon the implementation of the bean. Singleton is a design pattern that focuses on how beans are created, not how they are executed.
A singleton bean means there is one instance of the bean in the application context. All threads access the same class variables which can lead to inconsistency. Prototype scope on the other hand is thread safe but it is at the expense of performance because now there are multiple objects instead of one.





Explain prototype bean scope.#
Prototype scope means that every time the developer asks for an instance of the bean, the Spring container will create a new instance and return it. This is different from the singleton scope, where only one instance of the bean is created and the Spring container returns the reference of the same instance whenever it receives a request for the bean.



Does Spring manage the complete lifecycle of beans?#
Spring manages the lifecycle of beans from construction to destruction. However, this statement is not true in the case of prototype beans. The Spring container instantiates, configures and assembles a prototype object. But it keeps no track of the object after it is handed over to the client.
For a prototype bean, the initialization method is called but the destruction method is not called and the client is responsible for destroying the bean and releasing the resources that it acquired.
What is an inner bean?#
A bean which exists within the scope of another bean is called inner bean.




Inner beans are always anonymous and have prototype scope.


Spring Annotations:

201

What is an inner bean?#
A bean which exists within the scope of another bean is called inner bean.
When a bean is used as a property of another bean, it becomes an inner bean. 
The container ignores the id or name tags for an inner bean. Inner beans are always anonymous and have prototype scope.



The inner bean is not accessible outside the scope of the outer bean.



Spring Annotations:
What is the difference between @Component, @Service, @Repository, and @Controller?#
A typical application is divided into layers. The @Component annotation is generic and denotes any Spring managed bean. It can be used in any layer of the application whereas the other three are specific to layers. @Controller is used in the web layer, @Service is used on classes in the business layer and @Repository is used in the data layer and provides the additional functionality of making unchecked exceptions translated as Spring DataAccessException.
Why is @Primary annotation used?#
When two beans of the same type qualify to be autowired, then @Primary annotation is used to break the tie.

Why is @Qualifier annotation used?#
If more than one bean of the same type exists, we can choose the bean to be autowired using the @Qualifier annotation. The bean having this annotation qualifies to be autowired.


Which annotations takes precedence: @Primary or @Qualifier?#
When both the @Primary and @Qualifer annotations are present, then @Qualifier takes precedence. @Primary defines a default value and bean marked with this annotation will be used unless otherwise indicated. @Qualifier annotation is specific and is used when a particular bean is needed.


Suppose there are two beans of the same type and one is used in 90% of the cases, then it makes sense to make it the default choice by using @Primary annotation. The @Autowired that needs the other bean can use the @Qualifier annotation while all other @Autowired will automatically choose the bean marked with @Primary.


Why is the @Required annotation used?#
@Required is a method level annotation. It is used on setter methods and makes setter injection of the property mandatory. The BeanInitializationException is thrown if the property value is not initialized. If a setter method has @Autowired annotation on it, then @Required is not needed.


This annotation has been deprecated because constructor injection is used for setting all mandatory dependencies.

What is the purpose of @Autowired annotation?#
@Autowired annotation specifies where and how autowiring is done. This annotation can be used on setter methods, with a constructor argument, on a property as well as on methods with multiple arguments. By default autowiring is done by type.
Both @Bean and @Component annotations create beans. What is the difference between the two?#
Some differences between the two annotations are:
•	@Component enables Spring to auto-detect and auto-configure beans while @Bean is used to explicitly declare a bean rather than letting Spring auto-detect it.
•	@Component is a class level annotation while @Bean is a method level annotation.
•	Since @Component annotation is used on a class, it keeps the bean definition and class declarations together while @Bean decouples them



@Inject and @Autowired in Spring:

Both these annotations perform the same function and are used for dependency injection by type. The order of dependency injection of both the annotations is as follows:
1.	By type
2.	Using @Qualifer annotation
3.	By name.



The only difference between both annotations is that @Inject is a CDI annotation which makes it framework independent and @Autowired is a Spring framework annotation. Thus using @Inject may be helpful if the application is moved to another framework.






What is component scan?#
Component scan is the process in which Spring searches for beans. Spring needs to know the location (package) to search for beans. Component scan can be defined in two ways:
•	Using the @Component annotation and its sub-classes in which case Spring searches all the packages and sub-packages containing these annotation.
•	Using XML configuration with &ltcontext:component-scan> tag specifying the base package.


In Spring Boot, the @SpringBootApplication annotation triggers a component scan on the package and its sub-packages where it is used.

What is the difference between context: annotation-config and context:component-scan tags?#
&ltcontext: annotation-config> enables the detection of dependency injection annotations like @Autowired, @Qualifier, @PostConstruct, and @PreDestroy`.
&ltcontext: component-scan> specifies the base package for component scan. Component scan is used for finding beans. This tag can recognize the dependency injection annotations mentioned above as well as bean annotations like @Component, @Repository, and @Service etc.


What is autowiring in Spring?#
Connecting beans together in the Spring container is called autowiring. 

different modes of autowiring in Spring?
no autowiring in which case the developer has to provide explicit bean reference using the ref attribute
byName
byType
constructor


How does autowiring internally work?#
Spring calls the setter method for the property when autowiring mode is byName and byType

When autowiring mode is constructor and the class defines multiple constructors, then Spring will call the constructor with the most number of parameters


What is autowiring by constructor?#
Autowiring by constructor is similar to autowiring by type. It is applied to a constructor argument. 

What are the limitations of autowiring?#
•	Autowiring cannot be used for primitive data types like String and int. It can only be used for object references.
•	Autowiring is not explicit, so it may lead to unexpected behavior. It is better to do explicit wiring of bean dependencies.
•	It is possible to override autowiring if the dependencies are specified 
•	Autowiring is lookup based and can be expensive in large applications


What does the @Autowired annotation do?#
The @Autowired annotation can be used to guide Spring framework how autowiring is to be done. This annotation can be used on fields, setter methods or with constructor arguments.


By default, it uses dependency injection by type. This annotation is often used with @Qualifier to remove the ambiguity when more than one beans of the matching type are found


What happens if we specify an interface instead of a class in getBean() method?#
We can pass an interface to a method and behind the scene, Spring casts the object. It behaves in the same way as getBean(String). Type safety is ensured when casting and BeanNotOfRequiredTypeException is thrown if bean of the same type is not found


ClassCastException cannot be thrown on casting the result correctly as can happen with getBean(String) method.
Why do we need a no-arg constructor?#
When we do not define a constructor for our class, the compiler defines a default one for us. But when we declare a parameterized constructor, the compiler does not create the default one. If we are creating an object without passing any arguments, it will need the default no-arg constructor. If it does not exist in the code, we need to explicitly define a no-arg constructor.
What is Spring Security?#
It is a Spring module that provides authentication and authorization functionality to Spring MVC applications. It also provides the PasswordEncoder interface to secure user passwords. Spring Security takes care of common security vulnerabilities.
Spring security intercepts a user request and checks if the user is authorized to access the protected resources. It reads the application’s security configuration and also looks at the user’s passwords and roles to see if the user is authenticated and authorized to access the web resource.




What is the purpose of @RestController annotation in Spring Boot?#
The @RestController annotation combines the @Controller and @ResponseBody annotation. This annotation eliminates the need to annotate methods that map requests with the @ResponseBody annotation thereby making the code cleaner. The @ResponseBody annotation serializes the return object into HttpResponse.


What is the purpose of @ConditionalOnMissingBean annotation?#
This annotation is used with the @Bean annotation and tells the auto configuration class to initialize a bean only when it cannot find it in the application context. If the bean of that type already exists, then it will not be created.


@ConditionalOnMissingBean
@Bean
public MyBean myBean() {
    return new MyBean();
}


myBean will be initialized only when no other bean of type MyBean exists in the context. If it does, then myBean will not be registered as a bean.

The main purpose of this annotation is to provide a fallback bean, in case no bean of that type is present

What is an embedded server in Spring Boot?#
Embedded server means that the server is included in the application JAR and does not need to be deployed separately. Tomcat is the embedded server in SpringBoot applications. Embedded server makes the deployment of web applications easy and independent.



Can we change the default embedded server to Jetty?#
Tomcat is the default web server that comes with spring-boot-starter-web. To change the web server to Jetty, we will exclude tomcat dependency and add jetty dependency.
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
    <exclusions>
        <exclusion>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-tomcat</artifactId>
        </exclusion>
    </exclusions>
</dependency>

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-jetty</artifactId>
</dependency>



How are Spring Boot web applications deployed?#
Spring Boot web applications can be deployed as Jar or War files. Traditionally web applications were deployed as War files so as to save memory on the server. However now large size Jar files can also be deployed since hardware is cheap.



Spring provides a plugin to package a web application. This can be included in the pom file as follows:
<plugin>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-maven-plugin</artifactId>
</plugin>
The <packaging> attribute can be used to change the packaging to War. The default value is Jar.
We will get a deployable jar or war file after the Maven Package phase is executed.



How can the default web server in a Spring Boot application be disabled?#
The spring.main.web-application-type=none property in the application.properties file can be used to disable the default web server and change the web application type.



Only one dependency is needed in the pom file for the starter, for example, spring-boot-starter-web that contains all the required dependencies for a web application.




What is spring-boot-starter-parent?#
By using spring-boot-starter-parent in our project, we can reuse the default settings of Spring Boot. spring-boot-starter-parent defines the default java version, default encoding as well as plugin configuration for different plugins like maven-failsafe-plugin, maven-jar-plugin etc. It also specifies the working combination of dependencies and their version numbers. Everything in the parent plugin is inherited by the child pom. 


How can we connect Spring Boot with databases?#
The spring-boot-starter-data-jpa is used to connect a Spring Boot application to relational databases using JPA. When using JDBC, Spring Boot provides classes like JdbcTemplate, NamedParameterJdbcTemplate and DataSource that can be used to efficiently connect to, and perform database operations.
What does the exclude attribute of the @SpringBootApplication do?#
The exclude attribute, when used with the @SpringBootApplication annotation is used to exclude a package from component scanning. This attribute is used without the basePackages filter.




What is Spring Actuator?#
Spring Actuator provides data about the application that can be used for performance analysis as well as debugging. The data provided by Actuator includes, among many other things, the health of the application, beans created, controller mappings, and memory used etc. The Actuator endpoints are secured using Spring Security.



How can you create custom endpoints in Spring Boot Actuator?#
The @Endpoint annotation is used to create custom endpoints. To create a new endpoint, we can create a class and annotate it with the @Controller annotation along with the @Endpoint annotation.




Spring Data JDBC and JPA
Spring Data JDBC#
How does Spring provide DAO support?#
Spring DAO support makes it easy to work with different data access technologies in a consistent way which makes it easy to switch between technologies like JDBC, Hibernate, or JDO. Main features of Spring DAO support are:
•	Exception handling. Technology specific exceptions like SQLExceptions are translated to Spring’s DataAccessExceptions. Checked exceptions in Hibernate, JPA, and JDO can be converted to runtime exceptions.
•	Abstract DAO support classes. Spring provides abstract classes for different data access technologies which provide methods for data source and other configuration settings. These include the JdbcDaoSupport, HibernateDaoSupport, JdoDaoSupport, and JpaDaoSupport classes.



Describe Spring DAO support classes.#
Spring provides technology specific abstract classes for DAO support. These classes have methods for providing data source and other configuration settings specific to the data access technology. Abstract DAO support classes are:
•	JdbcDaoSupport class requires DataSource and returns JdbcTemplate instance.
•	HibernateDaoSupport class requires SessionFactory and returns HibernateTemplate instance.
•	JdoDaoSupport class requires PersistenceManagerFactory and returns JdoTemplate instance.
•	JpaDaoSupport class requires EntityManagerFactory and returns JpaTemplate instance.
What annotation is used to mark DAO in Spring?#
The @Repository annotation is used for DAO classes. This annotation provides the Spring exception translation facility which converts a technology specific expectation to a DataAccessException.




What is Spring Data JDBC?#
Spring Data JDBC framework is part of Spring Data. It provides support for JDBC repositories. Spring Data JDBC is a simple but limited ORM. It does not implement features like caching, lazy loading, and write-behind. Unlike Spring Data JPA, it does not provide schema generation and the developer must explicitly create the schema.
Spring JDBC uses methods like update(String sql), execute (String sql), and query(String sql, ResultSetExtractor rse) to interact with the database.
What tasks are performed by Spring JDBC?#
Spring JDBC is designed to reduce boilerplate code. It performs the following tasks:
•	Opens the connection
•	Prepares and executes statement
•	Iterates over the resultset
•	Handles any exceptions that arise
•	Manages the transaction
•	Closes the connection



What are the advantages of JdbcTemplate in Spring?#
The JdbcTemplate class uses the JDBC API to connect to a database and execute SQL queries. JdbcTemplate class removes the need to write boilerplate JDBC connection management code. It also removes the need for manual exception handling.`
Why is NamedParameterJdbcTemplate class used?#
The NamedParameterJdbcTemplate class is used to pass a value to a named parameter. It is better than a prepared statement with question marks. When we use names instead of ? it is better to remember the data in the column.



How are records from a database fetched when using JdbcTemplate?#
The query method of the JdbcTemplate class is used to fetch records from a database. The results are mapped using either the ResultSetExtractor, or the RowMapper interface.
What is the difference between a RowMapper and ResultSetExtractor?#
The RowMapper is executed for every row. It keeps looping over the result set and makes it available one row at a time. On the other hand, the ResultSetExtractor fetches all the records at once.
RowMapper is used when each row maps to a single object, e.g., return a list of players along with their country.
If we need to map multiple rows returned by a query to a single object, ResultSetExtractor is the appropriate choice, e.g., return a list of countries along with the number of players from that country. ResultSetExtractor allows manipulation of data as all rows of the result set are available at once.





Explain Spring’s exception handling support with DataAccessException.#
DataAccessException is a kind of runtime exception. It wraps technology specific exceptions to let the developer handle errors without knowing the details of the data access API which means that it is possible to catch JDBC exceptions in a generic way without knowing that JDBC is being used in the DAO layer. This allows one to change between data access technologies (e.g., JDBC, JPA, Hibernate) without changing a lot of code.
The developer need not write catch blocks for runtime exceptions.
What is SQLExceptionTranslator?#
The SQLExpectionTranslator interface translates a SQLException to Spring’s DataAccessException. The returned exception contains the original SQLException as the root cause.



What is the difference between CrudRepository and JpaRepository?#
CrudRepository provides CRUD operations.
JpaRepository extends the PagingAndSortingRepository which extends the CrudRepository.
JpaRepository provides methods for pagination and sorting of records in addition to CRUD operations.



Which ORMs are supported by Spring?#
Hibernate, JDO, Oracle TopLink and OJB are supported by Spring


What are the different types of transaction management supported by Spring?#
Spring provides support for both programmatic and declarative transaction management. Programmatic transaction management offers more flexibility but it is difficult to maintain as it requires controlling transactions through code. The transaction management code is tightly bound with the business logic as the developer is responsible to manually commit or rollback a transaction.
In declarative transaction management, the business logic and transaction management code is separate. Transactions are implemented as a cross-cutting concern or by using the @Transactional annotation.



Which transaction management type is preferred in Spring?#
Declarative transaction management which separates transaction management from the business logic is preferred because it can be implemented as a cross-cutting concern.
What are some benefits of using Spring Transactions?#
•	Spring transaction management allows the developer to handle transactions across different data access technologies in a consistent way.
•	Declarative transaction management is implemented using the Spring aspect-oriented programming and does not impact application code.
•	Programmatic transaction management API offered by Spring is simpler as compared to Java Transaction API.



What happens when the @Transactional annotation is used on a method?#
The @Transactional annotation is used in declarative transaction management and is used to handle transactions. It is based on the AOP concept.
Under the hood, the @Transactional annotation behaves in the same manner as the transaction advice. Spring creates a proxy around the bean to inject transaction management behavior before, after or around the method calls on the bean.
The @Transactional annotation supports both local and global transactions. It can only be applied to public methods.
What is the difference between JdbcTemplate and JPA?#
In JdbcTemplate, the database schema is not accessed via a domain model. JdbcTemplate allows more flexibility as it works on a lower level, but it also increases boilerplate code.
JPA requires that the database schema is mapped to a domain model. It makes interacting with databases simpler.



What is Spring MVC?#
Spring MVC is the module of Spring that implements the front controller and MVC design pattern. It provides a decoupled approach to developing web applications.
In Spring MVC, the three components of the MVC architecture, the front controller, view resolver and model are not dependent on each other. All incoming requests are handled by the front controller which is called the DispatcherServlet.



What are the advantages of using Spring MVC?#
pg217


the advantages of using Spring MVC?#
•	Spring MVC is based on interfaces which are independent of each other allowing separation of concerns.
•	Because there is no explicit dependency between the interfaces, Spring MVC applications are easily testable


flow of request in the MVC architecture?#
The dispatcher servlet is the front controller which receives all requests from the client. It has a mapping of all controllers and maps the incoming request to the appropriate controller.
The controller executes the request and returns a model and view name to the dispatcher servlet. The model contains the results.
The dispatcher servlet uses the view resolver to resolve the name of the view and populates it with results from the model and displays it to the client as a web page.



What is the Front Controller Pattern?#
Front Controller Pattern is a design pattern in which request handling is centralized. All client requests go to the front controller which contains a mapping of all controllers/servlets. The front controller maps the client request to the relevant controller/servlet, receives the results back, and renders the view to the client.
In Spring DispatcherServlet is the front controller. It receives all the requests from the client and forwards them to the appropriate controller.
Describe the function of the DispatcherServlet.#
The DispatcherServlet is at the heart of Spring MVC. It is the front controller which handles all the HTTP requests and responses.
The dispatcher servlet uses a configuration file containing information of all controllers and the URL mappings to forward an incoming request to the correct controller. It gets a model object and view back from the controller. The dispatcher servlet then forwards the view name to the view resolver and renders the response back to the client.


How does the dispatcher servlet map a request to a controller method?#
The dispatcher servlet uses handler mappings and annotations like @Controller and @RequestMapping to map a request to a controller method.
The HandlerMapping interface provides a mapping between requests and handler objects. Spring provides implementations of this interface where incoming request URLs can be mapped to controller classes.



Web applications and REST APIs differ in their return types with the former returning a view comprising of HTML, CSS and JavaScript while the later returning JSON or XML data.
The @Controller annotation populates the model map and returns a view name that is sent to the view resolver. The @RestController annotation returns an object which is written to HTTP response as JSON or XML.



The @RestController annotation is a combination of @Controller and @ResponseBody annotations. To return JSON or XML in a web application, we need to use the @ResponseBody annotation explicitly with the @Controller annotation.


Usually, the @RequestMapping annotation is used to map a single path to a controller method but this is not a rule. Multiple mappings can be specified in the value attribute as can be seen from the following example:
@RequestMapping(value = { "/hello", "/hi" })
@ResponseBody
public String multipleMapping() {
    return "Hello World!";
}
Both /hello and /hi are mapped to the multipleMapping method which returns a String response.



We can have multiple methods in the controller with the same request mapping as long as the request method is different. In the following example, /userForm is mapped to both the showForm and processForm methods. One method is for GET request while the other is for POST request.

What is an ambiguous mapping error?#
When Spring finds more than one controller methods having the same URL mapping, HTTP request method, parameters, headers and media type, it throws the ambiguous mapping error because it cannot choose which controller method to map the incoming request to. Changing anything from the above mentioned list to differentiate the controller methods will resolve this error



The value returned by a controller method is resolved to a view name. However, if we want to write directly to the response body, we use the @ResponseBody annotation to tell Spring that instead of resolving the return value as a view name, it should be displayed to the client as a String.



What is AOP and how does it relate to OOP?#
AOP stands for Aspect Oriented Programming. It divides the application logic into parts called concerns. AOP is similar to OOP in terms of modularity. It differs from OOP in the way modularity is defined. In OOP modularity is achieved by using classes whereas in AOP modularity is achieved using aspects that are applied to different class methods. Since aspects or concerns apply to the whole application, their processing should be centralized.
What is a cross cutting concern in AOP?#
A cross cutting concern is something that affects the whole application. Instead of handling it separately in every layer, it is handled in a centralized manner. Examples of cross cutting concerns are security, logging, transaction management, and error handling etc.
Is there a difference between the terms concern and cross cutting concern in Spring AOP?#
Concern can be defined as the functionality of a particular module in the application. For example in an e-commerce application, concerns may be inventory management and user management etc.
A cross cutting concern is a concern that is applicable across multiple application layers. For example logging and security functionality is needed by every module of an application.
What problems does AOP solve?#
AOP modularizes the code in terms of cross cutting concerns. The absence of AOP leads to two main problems.
•	Code tangling: the code for the cross cutting concern gets mixed with business logic.
•	Code scattering: Identical code is present in all modules.
Name some implementations of AOP?#
Popular implementations of AOP include Apache AspectJ, JBoss by Red Hat and Spring AOP.
What is the difference between Spring AOP and AspectJ AOP?#
Spring AOP does weaving at runtime using proxy while AspectJ does compile time weaving using AspectJ Java tools.
Only method level pointcuts are supported by Spring AOP while AspectJ also supports field level pointcut.
How does Spring implement a cross cutting concern?#
Spring AOP separates the business logic and cross cutting concern. The developer focuses on the program logic. Spring provides many aspects for cross cutting concerns which can be woven into the application.
What is a proxy in Spring AOP?#
In simple words, a proxy is an object that looks like another object but has some added functionality. In Spring AOP, proxy is the object created after applying advice to a target object.
Proxy = Advice + Target Object
Target object is also called a proxy object.
What is a target object?#
Target object is an object to which a cross cutting concern has been added. It is also called advised object or proxy object.
What advantage does Spring AOP provide?#
Spring AOP allows us to add or change a concern without having to change the application code. Since we separate the concerns from the application logic, concerns can be dynamically plugged in before, after or around the application logic. The code also becomes easy to maintain. Another advantage is that the developer can concentrate on business logic rather than the cross cutting concerns.
Spring AOP configures aspects as normal beans. Also, no special compilation unit is needed when using Spring AOP.
What is a JoinPoint?#
JoinPoint is a point in the program such as method execution where an aspect can be plugged in. There are different types of JoinPoints like field access, error handling and method execution.
Spring AOP only provides support for method execution join points. Any method inside the class can be called a join point if any cross cutting concern is applied to it and an aspect’s code is inserted into the normal flow of the application.
What is advice?#
The logic of the aspect is called advice. It is the action that is taken when an aspect is executed. In terms of programming, advice is the execution of the method where a joinpoint matches a pointcut.
List the different types of advice in AOP?#
There are 5 types of advice:
•	Before
•	After
•	After Returning
•	After Throwing
•	Around
Which advice type is appropriate for a try catch block?#
In order to try and catch exceptions, the @AfterThrowing advice type is used. The method annotated with this annotation is run after the method exits by throwing an exception.
What is the difference between Joinpoint and ProceedingJoinPoint?#
Proceedingjoinpoint extends the Joinpoint interface.
Joinpoint is used with the @Before, @After, @AfterReturning and @AfterThrowing advice types.
Proceedingjoinpoint is used with @Around advice. The @Around advice type is different from the rest because it can control when/if a method is executed. It also has a return value.
What is pointcut?#
Pointcut is the expression that is matched to a JoinPoint to determine whether the advice should be executed or not. Spring framework uses the AspectJ pointcut expression language. These contain matching method or class name patterns.
What is a named pointcut?#
When we need a pointcut at multiple places in the application, rather than using the lengthy pointcut expression, we can give it a name. This is done by creating a pointcut configuration class where we associate every pointcut with a method. Now the method name can be used in place of the long pointcut expression.
What is an Aspect?#
An aspect is a class denoted by the @Aspect annotation. It contains advice and joinpoints. Aspect defines a concern that cuts across multiple application layers.
What is weaving?#
Weaving is a process in which the aspects are plugged in at different points in the program execution. In Spring AOP, weaving is done at runtime. AspectJ provides both compile-time and load-time weaving.
When does the Spring framework perform weaving?#
Spring framework performs weaving at runtime. The process of weaving aspects into the application classes takes place when the classes are being loaded in JVM.
Which AspectJ Pointcut Designators are supported by Spring AOP?#
Spring provides support for some of the AspectJ Pointcut Designators (PCD) that can be used in pointcut expressions. For example:
•	execution: matches method execution joinpoints
•	within: matches to joinpoints of certain types
•	this: matches to joinpoints where the target object is of a given type
•	args: matches to joinpoints where the arguments of the given type
•	@annotation: matches to joinpoints where the method has a given annotation
Are there any limitations of Spring AOP?#
•	Spring AOP only supports method level joinpoints.
•	Advice is only applicable on public methods. Methods with private or protected visibility cannot be advised.
•	When weaving with proxies, advice is not executed on local method calls.
•	Aspects can only be applied to Spring beans.




Designpatterns
Strategy
Singleton
Observer
Factory
Abstract factory
Template
Adaptor
Decorator
Faced


 





 



