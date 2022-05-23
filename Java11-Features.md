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
