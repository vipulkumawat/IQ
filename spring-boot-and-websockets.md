**building-real-time-web-apps-with-spring-boot-and-websockets**

```
Pre-requisits:
Enterprise java development concepts and design patterns
Springframework
basic javascript
Eclipse or Intellij

Apps:
Whatsapp
O365
Facebook
Evernote
slack
snapchat
Dropbox
Instagram
Google drive
Linkdin
Twitter
Telegram
Uber



Websockets 101
Before 2001: synchronous HTTP(meant long waits for user)
2001: Asynchronous requests introduced(XHR is born)
2005: Ajax frameworks put XHR in the spotlight(shorter perceived waits for users)
2011: Socket based bidirectional web client/server communication(less waiting and more interactive experiences possible)

STOMP: Simple text oriented message protocol
connect()
subscribe()
send()
onmessage()

Our App Dev goals:
Server side:
Message Broker
Spring MVC related components
Unit tests for controller and message broker

Client side:
Simple webpage for GUI
Javascript for custom chat features

message broker is heart of the chat app

A websocket server needs a message broker to manage message destinations(queues) and relay data between clients and other application code(ex controller)

websocket protocol is bidirectional which means the client can subscribe to a topic and a service can publish topic updates to a client.

once a connection is established both client and server can exchange the information endlessly until conneection is closed by any of the parties.
for this reason a websocket typically preferred over A2DP when the client and server need to exchange information at high frequency
and with low latency because A2DP connections are closed once a request is served by the server
and there is time constraint to open a A2DP connection again

MessageBroker:
Implemented registerStompEndpoint()
Configured destination prefix("/topic")
Configured app URI("/app")

Integration Test Scope
Client(emulated)
connect()
subscribe("/topic/guestchats")
send("my message")

MessageBroker(handleSend("my message"))
Controller

An Integration test allows us to get instant feedback on the configuration and implemenatation of major server




```