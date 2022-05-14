**gRPC**

```
Microservices need to agree on:
API to exchange data
Data format
Error Patterns
Load balancing
Many other things...
Building an API is hard:
We need to think about:
Endpoints:
-GET /api/v1/user/123/post/456
-POST /api/v1/user/123/post

-DataFormat:
-XML(heavy, somehow readable)
-JSON(heavy, readable)
-Binary(light, not readable)

Invoking and Handling Errors
-Behaviors
-Error codes


We need to think about:
-Payload size
-Latency
-Scalability
-Load Balancing
-Languages Interop
-Auth, Monitoring and Log

Don't you wish you could just focus on data and leave the rest to the framework?
This is where gRPC comes in.
It is an opensource framework developed by google,square, github and other companies

gRPC is now part of cloud native computation just like docker, kuberneties and others

It is fast and efficient framework built on top of HTTP2.
it has low latency and super streaming of data.
It is language independent and makes it super easy to plugin new services like Authentication, logging, monitoring

what is RPC?
Remote procedure call
it is like calling a function directly on server

gRPC server
gRPC Stub

How do I get started?
There are really 2 steps:
choose a supported language
Generate the code(protobuff)

ex:
syntax="proto3";
message Greeting{
string first_name=1;
}

message GreetRequest{
Greeting greeting=1;
}

message GreetResponse{
string result=1;
}

services GreetService{
rpc Greet(GreetRequest) return(GreetResponse){}
}


Why ProtoBuff?
-Language agnostic
-small payload
-Easy API evolution

You should be familiar with Protobuff

Why learning gRPC?
Many companies using it like: 
Google for internal and external services like pubsub, Cisco, Netflix, CoreOS, Juniper,Squre, Cockroach Labs
Future of:
Microservice APIs
Microcontrollers/Mobile to server APIs
and web apis in future

Course Structure:
Theory
Practice
Advanced concepts

you will be able to:
Understand how gRPC works
Compare REST to gRPC
Write your own services
Implement advanced concepts

You will need:
Familiarity with language
Familiarity with ProtoBuffs
Basic Knowledge of Async Programming

Bust most importantly:
williness to learn new things

https://github.com/Clement-Jean
https://www.linkedin.com/in/clement-jean/
https://clement-jean.github.io/


The code is available at: https://github.com/Clement-Jean/grpc-java-course , don't hesitate to star the repo and to contribute.


Protocol Buffers and Language Interoperability:
Protocol buffers we define the messages,
we define the data for request and response
we define the service

why gRPC defines ProtocolBuff?
for communication between services because of payload size
normal json is compressed in Protocol buff.
we can save lot of bandwidth because messages are smaller
Passing JSON is also quite CPU intensive because format is human readable.
Protocol buffer is binary and it is very close to how data is represented in the memory.
it will be less CPU intensive
Protocol buffers are faster and more efficient communication between devices that are mobile and microcontrollers etc.
We will get better performance with protocol buffer than JSONs.


grpc.io
Intuitive Message Definition
Generated code for us
Efficient Serialization/Deserialization


HTTP/2:
it is a revolutionary technology which improved internet communication

impagekit.io
Performance difference between HTTP2 and HTTP1.0

How HTTP1 Works?
TCP connection per request until request is completed
for 100 calls 100 connections that is way too much
Plain text headers makes request header bigger consequence is bigger latency for each call
accepts only Request/Response pattern. If request/respone take long lived connection we will have more overhead
It accepts only GET/POST to manage resources at the backend.
opens a connection to get the resources


Http2:
one TCP connection with long lasting connection which can be shared by multiple request and responses
way more efficient
Server Push when data is ready
Multiplexing: server and client can push messages in parallel over same TCP connection
we can process requests and responses much faster as we have less latency
Http Headers are much lighter as headers and data are both compressed to binary data.
In HTTP2 protocol buffers are much really great match.
we can send binary messages using HTTP2 protocol.
HTTP2 is more secure SSL

So HTTP2 is 
less chatter
less bandwidth usage
More security
All of that for free!

https://http2.github.io/
https://imagekit.io/demo/http2-vs-http1

Types of gRPC APIs: 4 types
Unary
Server Streaming
Client Streaming
Bi directional Streaming


Unary:
Client sends request and server responds

Server Streaming:
client send one request and server can return one or more response depending on need.
this might be interesting where client want to get updated on real time basis like getting list from server

Client Streaming:
client send multiple request, server respond one response
useful when we do upload of information or realtime update of information

Bidirectional Streaming:
client and server can send multiple request and responses in parallel
request and response can arrive in any order
it can get response per request or response for two requests etc...



Types of API in gRPC:
service GreetService{
//unary
rpc Greet(GreetRequest) returns (GreetResponse){};

//server streaming
rpc GreetManyTimes(GreetRequest) returns (stream GreetResponse){};

//client Streaming
rpc LongGreet(stream GreetRequest) returns (GreetResponse){};

//Bi directional streaming
rpc GreetEveryone(stream GreetRequest) returns (stream GreetResponse){};


}



Scalability in gRPC:
server is Async so main thread is not blocked and server can handle many requests in parallel
client: Async or blocking based on requirement. when response is critical for application we go with blocking
Google: 10Billion requests/sec


Security in gRPC(SSL):



```







