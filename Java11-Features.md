**Java11 Features:**
```
New Methods of String class
String value="";
value.isBlank();
trim method doesnot handle unicode of space
instead use strip
value.strip();
//to remove space from beginning and end of string
.stripLeading();
.stripTrailing();
//repeat method for repeating the string
value.repeat(times);
value.lines();
//to get array of string which are split by new line character in the string

With Java11, reading from text files is much easier now
Files.writeString(Paths.get("example.txt"), fileContent,StandardOpenOption.CREATE);
Files.readString(file.toPath());


Java 11 allows us to use var keyword for type inference
we can apply it to the argument of lambda function

BiFunction<String,String,String> lambda= (var var1,var var2)-> String.join(" ",var1,var2);
return lambda.apply(value1,value2);

we need to use this var if we need to apply any annotations

BiFunction<String,String,String> lambda= (@NonNull var var1,@NonNull var var2)-> String.join(" ",var1,var2);
return lambda.apply(value1,value2);

When we need to use annotation we need to provide the type. So we have added var for the arguments

calls to a URL:
var url=new URL("...");
var connection =(HttpURLConnection) url.openConnection();
connection.setRequestMethod("GET");

int statusCode = connection.getResponseCode();

var reader= new BufferedReader(new InputStreamReader(connection.getInputStream()));
String responseLine;
var responseBody=new StringBuilder();

while((responseLine=reader.readLine())!=null){
responseBody.append(responseLine).append(System.lineSeparator());
}

System.out.println(responseBody);
connection.disconnect();
return statusCode;


This is huge chunk of code for a single http call
so a new HttpClient very similar to Spring's Rest Template is added  in java11.

var client=HttpClient.newHttpClient();
var url=new URL("...");
var request = HttpRequest.newBuilder().GET().uri(url.toURI()).build();
var response = client.send(request,HttpResponse.BodyHandlers.ofString());
System.out.println(response);

return response.statusCode();

Java flight recorder

migrating-beyond-java-8
```

```
Java11+ features:
Suggested Courses:
Programming Foundations: Fundamentals
Programming Foundations: Object-Oriented Design

Java SE10:
Type Inference
Garbage Collector Interface
Time based release versioning


JavaSE11:
New Lambda Syntax
Dynamic Class file constants
New HTTP Client
Nashorn deprecated

JavaSE12:
Switch expressions
JVM Constants API
Abortable mixed collections


JavaSE13:
Many JVM and Garbage collecetor improvements
More in switch expressions



Keywords throught Java8:
https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html


Memory management:
local variables and function calls are stored on stack
objects and member variables are stored in heap

objects are retained in  memory until dereferenced
Garbage collector is a background process.

Tips for managing memory:
Minimize the no of objects you create
system methods that report memory usage
Runtime.maxMemory()
Runtime.totalMemory()


Inferred Data types:
Starting in java10, local variables can use type inference
Type is derived from the assigned value

var myVar=5;

var emp=new Employee();
type inference works only for local variables inside methods or within JShell


double value=.012
double sum=value+value;
expected: 0.024
result: 0.0240000004

this results in issue due to precession
This can be solved with BigDecimal

var strValue=Double.toString(.012);
var bigValue=new BigDecimal(strValue);
var bigSum=bigValue.add(bigValue).add(bigValue);

var sum=bigSum.doubleValue();


Widening and Narrowing


```
