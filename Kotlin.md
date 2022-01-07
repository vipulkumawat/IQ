Kotlin Development Master Class
--------------------------------
Language Basics
Object Oriented Programming
Projects
Practice Practice Practice


Intro
Concept
Practice Exercises
Challenge

Intellij Idea

FirstCode:
Section Objective

REPL
Read Evaluate Print Loop

Variables and Strings:
Strings: Chain of zero or more characters surrounded by double quotes
Chars: A char is a single character surrounded by a single quotes
A string is composed of characters(string of chars)
Variables: is like a container of data
ex:
var var_name="varString"
var dogs=3
var age=25
age=26
var newAge=age+1
we can change the value of a variable but cannot change a variable's type

variables are of two types:
Changeable(Mutable)- var
Read only(immutable)- val


Variable names: can contain letters, numbers, underscores _, 
Names must start with a letter or _
Names can be anything except Kotlin keywords
Naming convention- camelCase - myDogIsFunny

String Specific Functions:

String templates:
Strings in kotlin can contain expressions
The expression is evaluated and inserted(concatenated) into the string
An expression starts with a $ sign and can have {}
val dogname="Teddy"
print("My dog's name is $dogName")
can have expressions in the string

Lots of exercises
Strings and expressions
Constants: values that donot change
Are available at compile time and are not calculated during program execution
Toplevel: are declared outside of functions
Convention: names are in all-caps

const val URL_LINK="google.com"	

fun main(args:Array<String>){
println(URL_LINK);

}


variables and Strings recap
Strings: what can they contain
variables: what they are and how to create them
variable names: what are valid names
String specific functions- how to manipulate strings and get information
String templates- how to add data to strings
Practice Practice Practice


UserInput:
Section Objective:
Get Input from the user
Transform the input into a number
UserInput can come from many sources
One way is from the command line
val userInput=readLine()
println("You said $userInput")

Input Number: Input is read as string
Can be converted into numbers(input)
The readline command can return nothing:(null)

val userInput=readLine()?:""
val myNumber=userInput.toInt()

3:40


video37:
Generating a random number:


Read from the console
Transform the input into a number
Intro to the elvis operator


Numbers and Variable types:
Numbers
Types of Numbers
Implicit vs Explicit definition
Convert one type to another
Talk about Strings some more


What are numbers in kotlin:
5
343434
-545
var price=23
var items=3
var totalprice=price*items


types of numbers:

Different types that are store in memory in different ways
Number types have limits
There is a biggest and smalles number of a certain type

How we store things in memory gives us some properties about those particular number

Byte: 1 byte: -128 to 127
Short: 2 bytes: -32768 to 32767
Int: 4 bytes: -2^31 to 2^31-1
Long: 8 bytes: -2^64 to 2^64-1
Float: 4 bytes: 6 to 7 decimal digits
Doublt: 8 bytes: 15 to 16 decimal digits

var items=5 //Int
var nbOfPeople=750000000 //Long
var price=29.99 //Double
var pi=3.14159494949 //Double

prinltn(pi::class.java) //double

this is equivalent to typeof operator.



How are numbers stored in memory:
Computer memory is composed of elements that can be on or off
on=1
off=0

one element is called a bit
8 elements are called a byte


Implicit vs Explicit values
---------------------------
implicit numbers are decided by Kotlin
val cats=3 //Int
Kotlin decides the most appropriate variable type based on the value provided
val price=14.99  //Double

We can instruct kotlin to assign a different type to our variables.

val cats=3     //Int
val dogs:Byte=5  //Byte
val days:Short=20000
val meals:Int=3
println(dogs::class.java)
println(cats::class.java)
println(days::class.java)
println(meals::class.java)



    //Type Conversions
    //toByte()
    //toShort()
    //toInt()
    //toLong()
    //toFloat()
    //toDouble()


    val dogs=5
    val byteDogs=dogs.toByte()
    val shortDogs=dogs.toShort()
    val intDogs=dogs.toInt()
    val floatDogs=dogs.toFloat()
    val longDogs=dogs.toLong()
    val doubleDogs=dogs.toDouble()


    println(dogs)
    println(byteDogs)
    println(shortDogs)
    println(intDogs)
    println(floatDogs)
    println(longDogs)
    println(doubleDogs)

	

	String
	Every variable in kotlin has a type
	val name="John"
	val newName:String="Alice"
	Any variable ca be converted into a string before printing to console
	val cats=3
	val catsString=cats.toString()
	println(catsString::class.java)
	//class java.lang.String
	
	val pi=3.1415
	println(pi::class.java)
	val piString=pi.toString()
	println(piString::class.java)
	//double
	//class java.lang.String
	
	
	println("Please Enter a number")
	val numberInput=readLine()?:"0"
	val myByte=numberInput.toByte()
	println(myByte)
	println(myByte::class.java)
	
	
	Section7:
	Operators and Boolean
	
	
	
	Arthimetic Operations
	Result types
	Assignment Operators
	Booleans(true/false)
	Logical Operators:
	
	Operators-Result type
	the type of the result of an operation is the same as the type of the largest operand, in terms of size in the memory
	Byte<Short<Int<Long<Float<Double
	Result types:
	the type of the result of an operation is the same as the type of the largest 
	operand in terms of size in memory
	
	
	val a:Short=6
	val b:Int=32
	val r=a*b
	println(r::class.java)
	
	
	val a:Long=23232323324
	val b:Float=12.34F
	val result=a/b
	println(result::class.java)
	
	val a=23.344F
	val b=233444.5333
	val result=a*b
	println(result::class.java)
	
	Byte<Short<Int<Long<Float<Double
	
	val dozen=12
	val months=dozen
	println(months)
	
	
	
	
	
	Operators-Assignment:
	= Assignment
	$ Reference
	${}  Reference Expression
	
	
	val userName="Lucy"
	val greeting="Hello, $userName"
	println(greeting)
	
	val products=3
	val price=9.999
	val total="Total is ${products*price}"
	println(total)
	
	
	
	Operators- Augmented Assignment
	var bikes=5
	bikes+=1
	-=
	*=
	/=
	%=
	println("${a+b}")
	println("${a-b}")
	println("${a*b}")
	println("${a/b}")
	println("${a%b}")
	
	
	Booleans:
	True/false value
	val isDay=true
	val isNight=false
	Very Memory Efficient: uses only 1 bit
	Enable logical operations
	Enable program flow control
	
	Logical Operators:
	&& And
	true && true //true
	true && false //false
	
	fun main(args:Array<String>){
		val isDay=true
		val isEvening= true
		val isNight=false
		
		println(isDay && isEvening)
		println(isDay && isNight)
	}
	
	||
	println(isDay || isNight)
	val playtime=false
	println(isNight || playtime)
	
	println(!isDay)
	isNight=!isDay
	println(isNight);
	
	Comparision Operations:
	>
	val a=5
	val b=21
	println(a>b)
	println("$a > $b will return $(a>b)")
	println(a<b)
	println(a>=b)
	println(a<=b)
	println(a==b)
	println(a!=b)
	
	val expr1=5.34*45.34
	val expr2=3.455*15.3434
	println("Is $expr1 > $expr2 : ${expr1>expr2}");
	
	
	val expr3=((tr
	ue && false)||(true ||false))
	println(expr3)
	
	val toys=2
	val brokentoys=1
	val notbroken=toys-brokentoys
	val canGetNewToy=(toys<5 && notbroken>=1)
	println("Will the child get a new toy? $canGetNewToy")
	
	
	val noOfCows=3
	val milkProducing=1
	val noOfChildren=2
	val familyMembers=noOfChildren+1
	val getsFunding=(noOfCows<=5 && milkProducing>0 )||( familyMembers>=3)
	println("Will farmer receive funding? $getsFunding")
	
	
	
	Section8:
	Nullability:
	Section Objectives:
	Kotlin Provides some functionality that we avoid certain class of errors,
	this class of errors are called as Null Pointer Exceptions which are basically
	errors that happen when u try to perform some action on a variable that has no value. That usually crash programs and errors, generally creates bad user experience. Kotlin provide some tools to handle these errors and make sure they never ever happen. This is one of the key selling point of kotlin. Providing functionality to avoid null exceptions/errors.
	Null value
	Null Operators
	Elvis operator
	Non-null assertions
	
	
	video72:
	Null value
	No Value present
	If you use a variable with a null value, your program will crash with a NullPointerException(NPE)
	
	Kotlin gaurds against null values
	Kotlin differentiates between variables that can be null and those that cannot.
	using the ? operator
	val herName:String="Lilly"  //Cannot be null
	val hisName:String?=null // can be null because of ?
	If a variable cannot be null, it must be given a value
	If a variable can be null, giving it a value is optional in this case you must provide the value null
	
	println(herName);
	println(hisName);
	
	In kotlin you can declare a variable without assigning the value, but if u need to use a variable then you should definately assign a value to the variable
	
	val hisName:String?
	println(hisName)   //Compilation error
	
	The null keyword:
	The null keyword is used to assign the value null to a nullable value
	
	val catName:String?="Chonkers"
	catName=null  //Ok
	
	val dogName:String="Puggle"
	dogName=null //Compilation error
	
	you cannot assign null to a variable that is not nullable, that has to be defined with ?.
	
	Video73:
	Null Safe Calls or Null Operators:
	Those are operators that we can use and sometimes we have to use on null values or variables that can be null, 
	? Nullable operator
	var catName:String?="Check"
	catName=null  //Ok
	
	var catName="CheckNull"
	catName=null //Compilation error
	//null cannot be value for a variable of type non-null
	
Kotlin makes a distinction on variable that can be null and variables that cannot be null.


?. Nullable operator

var catName="Cat"
catName?.length
//returns either null if catName is null or actual string length


var catName="cat"
catName.length
//Always returns the string length since catName is certainly not null

safe calls can be chained for multiple operations

catName?.length?.toString()
//null
catName.length.toString()

	
Arithmetic Operators:
works only on variables which are not null
we cannot use the classic operators for null variables
we have replacement methods

+   as  ?.plus()
-   as  ?.minus()
*   as  ?.times()
/   as  ?.div()
%   as  ?.rem()


val a: Int? =10
println(a?.plus(3))
println(a?.minus(3))
println(a?.times(3))
println(a?.rem(3))

video75:
Practice Null:
var a:String? = "I like dogs"
println(a?.substring(3,6))


var d:Double?=13.69
b=b?.times(6)
var c=b?.toFloat()
println(c)

var username=readLine()
println(username?.length)

var num=readLine()
val dnum=num?.toDouble()
val dstring=dnum?.times(7)?.toString()
println("length of $dstring is ${dstring?.length}")

video78:
The Elvis Operator

?: Guarantees a result returned
Either the actual result for a non-null variable, or a default value.
If u have a null value inside our variable then we use default value, if the variable is not null, then use the value of our variable.

val catName:String?=null
println(catName?:"This cat has no name")
catName="Fluffy"
println(catName?:"This cat has no name")

val catName="Puggle"
println(catName)

After an elvis operator, there's no need for null safety because the elvis operator guarantees a value.


 println(catName?:"Fluffy".length)
 
 
 video79:
 Non-null Assertions
 !!. A developer guarantee that the variable is not null
 
 Warning: This bypasses all the language checks for null safety , Can trigger a program crash
 
Try to avoid it as much as you can.
 
 val catName:String?=null
 println(catName!!.length)
 //If the value is null, the program will crash
 //kotlin.KotlinNullPointerException
 
 
 var catName:String?=null
 catName="Fluffy"
 println(catName!!.length)
 
 
Read a message from Console
Printout either the message or a default greeting.
println("Input a message")
val message=readLine()
println(message?:"Hello Message not received")

Read a numer from the console
Assume you know that the user has entered a value and the read variable is not null.
Multiply that number by 5 and print the result

println("Input a number")
val num=readLine()
val number=num?.toInt()
println("$number number multiplied by 5 is ${number!! *5}")


A product costs 29.99.
Ask a user at the console how many products they want to buy.
If the read value is null, use the default of one.
Print the total of the purchase.

val productcost=29.99
println("How many products you want to buy")
val noOfProducts=readLine()
val nop=noOfProducts?.toInt()?:1
println("Total of Purchase: ${nop*productcost}")


Nullability:
What a null value is and how kotlin manages it.
How to declare a nullable variable
How to make safe calls and avoid exceptions
How to use the Elvis operator to provide an alternative
How to assert that a variable is not null at a certain moment



Section9:
Exception Handling
Video84: Section Objectives

Exceptions
Try catch block
Finally block
Throw exceptions




video85:
What are exceptions:
Unexpected event in a program
The system cannot recover from an exception
Execution is stopped and data is lost
cause very bad user experience

var test=readLine()
println(test?.toInt())
//java.lang.NumberFormatException: for input string: ""

Exceptions have a message
A stacktrace: a log of what the program did before it reached this point

Optionally a cause

TryCatch:

A way to manage exceptions
var test=readLine()
try{
println(test?.toInt());
}catch(e:Exception){
println("An exception has occurred \n ${e.localizedMessage}");
}

we try to run a block of code
If an exception occurs, the code is the catch will be run
Execution can continue

fun main(args:Array<String>){

var test=readLine()
try{
println(test?.toInt())

}catch(e:Exception){
	e.printStackTrace()
	println("An exception happened \n ${e.localizedMessage}");
}
}

Optionally we can print the stacktrace
e.printStackTrace()
This is usually a good idea, as it will likely go into a log


video87:
Finally:
a finally block will be executed whether or not an exception occurs
var test=readLine()
try{
println(test?.toInt())

}catch(e:Exception){
	println("An exception has occurred\n${e.localizedMessage}")
	e.printStackTrace()
}finally{
	println("The execution has completed");
}


video88:
Throw
A way to generate your own exceptions
Can be used if you detect a state in your program that you cannot recover from
Using the keyword throw

throw IllegalStateException("I don't like this input")

import java.lang.IllegalStateException

fun main(args:Array<String>){
var test=readLine()
throw IllegalStateException("I don't like this input")
}


video89:
Practice: Try catch finally
Operators
Read data from the console and convert it into a number
If possible, multiply it by 5 and print
If an exception occurs, catch it and print a meaningful message.

fun main(args:Array<String>){
println("Please enter a number")
var inputNum=readLine()
try{
	print("result:${inputNum?.toInt().?.times(5)}")
}catch(e:Exception){
e.printStackTrace();
println("Please provide valid number:${e.localizedMessage}")
}
}
	
//NumberFormatException
	
	
fun main(args:Array<String>){
println("Please enter how many kilometers they ran today:")
var kms=readLine()
try{

var miles=kms?.toDouble()?.times(0.62);
println("No of miles:${miles}")
}catch(e:Exception){
e.printStackTrace()
println("Cannot read distance")

}
}	
	
	
video90:
Exercise: Try catch finally
A customer will tell the program what product they want to buy.

Then, they will tell the program how many products they require.

Assume the price of the product is 9.99

What is the total?

Handle any exceptions that might occur.

	
Exercise91:
Solution:
	
fun main(args:Array<String>){

println("what product you want to buy:");
var products=readLine()
println("How many would you like?")
var input2=readLine()
try{

println("What product do you want to buy?")
var total=input2?.toInt()?.times(9.99)
println("Total price:${total}")

}catch(e:Exception){
e.printStackTrace()
println("Invalid no of products entered")
}finally{
println("Transaction completed")
}
}
	
	
Handling Exception Recap:
What exceptions are and when they occur
How to handle them using the try catch block
How to execute code using the finally block
How to throw our own exceptions when necessary


Section10:Collections
video93: selection objectives
Section Objectives
Collections
Types of Collections
List
Set
Map
Iterator


video:94
why are cllections useful:
they are useful to handle n no of elements and do the same set of operations on them.


video95:
What are collections:
A way to group elements together.
Zero or more elements
All elements in the collection are of same type.

MutableIterable
Mutable Collection
Iterable
Collection
List
Set
MutableList
MutableSet

Map
MutableMap


A class is a structure that provides some functionality for a certain element. 
ie. add, remove, size,...


Map's are not collections, they are usually grouped inside collections discussion because they are conceptually same thing eventhough in practice they don't have same kind of functionality,



video96:
List:
Ordered Collection
Elements can be accessed by the position(index)
Indices always start with 0
Can contain duplicate elements
[1,2,3,4,2,6,5]

A sentence is a list of words:
They have an order and can repeat


video97:
Set:
----
Group of unique elements
You cannot have two elements of same type in the set.
In set order has no significance, we can go through the elements on by one(iterate over them) but the order is not defined.

A deck of cards is a set



video98:
Map
A set of key-value pairs, Keys are unique(set), Each key maps to exactly one value, values can be duplicates{1=one,3=three,5=five}
A dictionary is a map
Maps words to definations

video99:
Iterators:
An iterator is an object that loops through elements of a collection
Useful when applying the same operation to all elements.



Section100- recap:
Section101:
List and ArrayList:
List
ArrayList
ListFunctions
ArrayList Functions

List:
Ordered Collection that can contain duplicate elements
var color=listOf("Blue","Yellow","red")
println(color) //lists are immutable


fun main(args:Array<String>){

var colors=listOf("blue","yellow","green");
println(colors)
}

if we create an empty list, we must specify the element type

val colors=listOf<String>();
println(colors)

val colors=listOf("blue","red","blue","green","blue")
println(colors)

can contain nulls
var colors=listOf("blue","yellow",null,"blue","blue",null)
println(colors)

Retrieve an element of the list
As lists are immutable, we cannot add/remove elements in an Immutable list.however we can access elements of the list like retrieving elements of the list.

val colors=listOf("blue","yellow","red")
colors[0]
colors[2]
colors[5]  //ArrayIndexOutOfBoundsException

colors.get(1)

size of the list:
colors.size

video103: arraylist

A mutable(changeable) list

var colors=arrayListOf("blue","red")
println(colors)

val nocolors=arrayListOf<String>()
println(nocolors)


We can add elements
colors.add("yellow")
println(colors)

Add another collection
var moreColors=arrayListOf("pink","teal")
colors.addAll(moreColors)

colors.remove("red")
println(colors)

colors.removeAll(moreColors)
println(colors)

remove an element at position
colors.remove(1)
println(colors)

colors.add("red")
println(colors)

colors.add("blue")
println(colors)
colors.remove("blue")
println(colors)


var animals=listOf("Lion","monkey","zebra")

println(animals.size)
println(animals[1])

val customers=arrayList("Alex", "John","Michelle","Judy")

val newcustomer="Mickel)
customers.addAll(newCustomer)
println(customers)

val leavingCustomer="John"
customers.remove(leavingCustomer)
println(customers)


val items = arrayListOf(“laptop”, “mouse”, “pen”, “paper”, “mug”, “phone”)

val removedItems = listOf(“pen”, “paper”, “mug”, “phone”)

items.removeAll(removedItems);
println(items)

video107:
List Functions

val colors=listOf("blue","red","blue","green")
colors.size
colors.contains("red") //true
colors.contains("pink")  //false

val newcolors=listOf("red","green")
colors.containAll(newColors)

colors.indexOf("blue");

colors.lastIndex("blue");


function main(args:Array<String>){

val colors=arrayListOf("blue","red","blue","green")
colors.set(1,"redder")
println(colors)
val subcolors=colors.subList(1,3)
println(subcolors)
println(subcolors::clas.java)
}

ArrayListfunctions:

val colors=arrayListOf("blue","red","blue","green")
colors.set(1,"redder");
println(colors)
val subColors=colors.subList(1,3)
println(subColors)

println(subColors::class.java)

colors.clear()
println(colors)

colors.isEmpty()
println(colors)


video109:
Practice List Functions

val winners=listOf("Usain","John","Michael","Alex","Bob")
println("Michael finished on position ${winners.indexOf("Michael")+1}");

val requiredColors=listOf("red","green","blue")
val availableColors=listOf("red","blue")
println("Can print ${availableColors.containsAll(requiredColors)}")


A receipe calls for the following ingredients
Chicken
Egg
Mozzarella
Pepper
You decide to replace the Mozzarella with blue cheese
Print out the list of ingredients

val ingredients=arrayListOf("Chicken","Egg","Mozzarella","Pepper")

ingredients[ingredients.indexOf("Mozzarella")]="Blue cheese"
println(ingredients)



Exercise: List functions
A zoo has a list of animals.
val animals = arrayListOf(“lion”, “zebra”, “chimp”, “elephant”)
A new panda bear cub has arrived.
Print out the new list of animals.
The lion has been sold to a different zoo.
Print out the new list of animals.
Does the zoo have both elephants and giraffes?



val animals = arrayListOf(“lion”, “zebra”, “chimp”, “elephant”)
animals.add("panda")
println(animals)
animals.remove("lion")
println(animals)
val requiredAnimals=listOf("elephant","girafee")
println("Does the zoo have both elephants and giraffes? ${animals.containsAll(requiredAnimals)}")



SectionRecap:
What lists are and how to use them
What ArrayLists are and how to use them
List Specific functions
ArrayList specific functions


Section12:
Set and HashSet


Set
HashSet
Set Functions
HashSet Functions


video114:
What is set:
Store unique elements in an undefined order

val numbers=setOf(6,34,6,42)
println(numbers)


If we create an empty set, we must specify the type
val number=setOf<Int>()

A set can contain a null element, but only one

val num3=setOf<Int?>(6,5,3,4,null,2,3,null,6,9,null)
println(num3)
//it will not allow to add null values unless we specify nulltype
which is ? after the type
otherwise remove adding type only

video115:
HashSet

Set has a big problem, we cannot add or remove elements
with Hashset we can add or remove elements, it is a mutable set.

val numbers=hashSetOf(3,4,null,83,56)
val noNumbers=hashSetOf<Int>()
println(numbers)
println(noNumbers)

we can add elements to a hashset

numbers.add(44)
//[3,4,null,83,56,44]
println(numbers)

Add another set
newNumbers=hasSetOf(15,16)
numbers.addAll(newNumbers)

val newNumbers=setOf(45,36,78)
numbers.addAll(newNumbers)
println(numbers)

Remove an element
val numbers=hasSetOf(3,4,null,83,56)
numbers.remove(83)

Remove all elements of a set:
val toRemove=hasSetOf(3,4)
numbers.removeAll(toRemove)


video116:
Practice: Set and HashSet

create an empty set of String colors
Add three colors
Remove one
Print out the result

val colors=hashSetOf<String>()
val colorsList=listOf("red","green","blue","red")
colors.addAll(colorsList)
println(colors)

colors.remove("green")
println(colors)


val objects=hashSetOf("laptop","mouse","phone","bottle","cup")
val removeObjects=setOf("cup","bottle","phone")
objects.removeAll(removeObjects)
println(objects)




Exercise: Set and HashSet
You have a list of customers for your online store.
A new customer has joined.
Print the list of customers.
A customer has chosen to leave.
Print the list of customers.

//val cust=hashSetOf<String?>("Akil","Raju","Omar","Rohit")
val cust=hashSetOf("Akil","Raju","Omar","Rohit")
println(cust)
val customer=readLine()?:"
cust.add(customer)
println(cust)
val leavingCust=readLine()?:""
cust.remove(leavingCust)
println(cust)


video119:
Set Functions
.size
.contains(field)
.containsAll(setOf(4,5))
.isEmpty()

println(setOf<Int>().isEmpty())

.retainAll()
.clear()
.isEmpty()
.contains()


Your company has very strict dress code. Only certain color clothes can be worn in the office.
val acceptedColors = hashSetOf(“white”, “black”, “grey”)
You have certain colors in your wardrobe.
val myColors = hashSetOf(“blue”, “red”, “black”, “green”)
What color clothes can you wear.
Your company has added another color, “red” to their list. What options do you have now?

val acceptedColors = hashSetOf(“white”, “black”, “grey”)
val myColors = hashSetOf(“blue”, “red”, “black”, “green”)

myColors.retainAll(acceptedColors)
println(myColors)



Section13:
Map and HashMap

Map
HashMap
Functions

A map is a set of key-value paris
Keys are unique, values can be duplicates

var count=mapOf(Pair(1,"one"),Pair(2,"Two"),(3,"Three"))
println(count)

if we create an empty map,
we must specify both the key and value types

val count=mapOf<Int,String>()

Get a value based on a key
count.get(2)
count[2]

count.keys //gives whole set of keys

count.values


video127:
HashMap
Mutable Map
var count=hashMapOf(Pair(1,"one"),Pair(2,"Two"),Pair(3,"three"))
adding a key-value pair
count.put(4,"four")
adding all elements of another map
var countMore=hashMapOf(Pair(20,"Twenty"),Pair(30,"Thirty"))
count.putAll(countMore)

Remove an element:
count.remove(2)

.replace(1,"oneone")

.clear()


video128:
Map Functions

var count=mapOf(Pair(1,"one"),Pair(2,"Two"),Pair(3,"three"))
count.size
count.containsKey(2)
count.containsValue("three")
.isEmpty()
count[2]
count[3]
count.put(4,"quatre")
println(count)
count.get(3)



You manage an amusement park, and you have a map that stores dates and attendance.
var attendance = hashMapOf(Pair(“23 Sept”, 2837), Pair(“24 Sept”, 3726), Pair(“25 Sept”, 6253))
Add a value for 26 Sept.
How many people attended in total on 25 and 26 Sept?
Is data for 22 Sept available?

var attendance = hashMapOf(Pair(“23 Sept”, 2837), Pair(“24 Sept”, 3726), Pair(“25 Sept”, 6253))

attendance.put("26 Sept",100);
//attendance.get("25 Sept")+attendance.get("26 Sept")
//attendance["25 Sept"]?:0+attendance["26 Sept"]?:0
attendance.containsKey("22 Sept")


Section14:
Flow Control
video133: Section Objectives

Flow Control
If Conditional
When Conditional
For loops
While loops


FlowControl:
Change the direction of execution of a program
Make decisions
Run part of code multiple times
Stop execution of a part of code

IfConditional:
if condition then

else


When Conditional:
when variable or expression:

value1: do value1
value2: do value2
value3: do value3
default: do something


video137:
For loop:

video141:
If Statement

val night=(readlIne()?:"true").toBoolean()

if(night){
	println("sleep");
}else{
	println("Be active");
}



var clientFunds=100
val price=50
var clientProducts=0

if(clientFunds>price){

clientFunds-=price
clientProducts+=1
println("you have purchased $clientProducts products")
println("you have $clientFunds funds")

}else{
println("you have insufficient funds to purchase the products")
}




video142:
More if statements
Make decisions based on a logical expression


val petStore=listOf("cat","dog","rabbit")
val hasCatFood=false

if(petStore.contains("cat")){

if(hasCatFood){
	println("Buy Cat and cat food")
}else{
	println("By cat only")
}
}else{
println("Ask the pet store owner to get a cat")

}



Multiple branches:
val action=if(animal=="dog"){
"pet it"
} else if(animal=="cat"){
"feed it"
} else if(animal=="crocodile"){
"run away"
}else{
"google it"
}



val input=readLine()?:"0"
val number=input.toInt()
val outcome=if(number/10==0) "single digit number" else "Multi digit number"
println(outcome)



var response=readLine()?:404

val resptype=if(response/100==1) "Information response" else if(response/100==2)
"Success" else if(response/100==3) "Redirect" else if(response/100==4) "Client error" else "Server error"

println(resptype)



A -> 90 to 100
B -> 80 to 89
C -> 70 to 79
D -> 60 to 69
E -> 50 to 59
F -> everything else

var marksstr=readLine?:"0"
var marks=marksstr.toInt()
var response= if(marks>=90) "A" else if(marks>=80) "B" else if(marks>=70) "C"
else if(marks>=60) "D" else if(marks>=50) "E" else "F"

println("Grade for given  marks is: $response")





Section16:
Expressions

Arithmetic Expressions
Logical Expressions
Ranges
in and !in keywords
Boolean returning functions


video154:
in keyword


to check a value in collection
"cat" in listOf("dog","cat","horse")
3 in setOf(1,5,8,34)

to check a value in a range
5 in 1..10   //true
15 in 1..10  //false


val favoritePet="dog"
val availablePets=listOf("dog","cat","horse")

if(favoritePet in availablePets){
	println("We have your next best friend");
}else{
	println("Sorry, $favoritePet is not found");
}


!in keyword checks whether  a value is not in a collection

"cat" !in listOf("dog","cat","horse")  //false
3 !in setOf(1,5,8,34)

A value is not in a range 
5 !in 1..10
15 !in 1..10

val availableCoffee=listOf("capuccino","mocha")
if(coffee !in availableCoffee)
	println("Your coffee is not available")
	

println("Enter a number")
val input=readLine()?:"0"
val number=input.toInt()
if(number !in 0..9)
	println("your number is not a single digit")
	
Boolean returning functions:
A function can be used in a conditional statement if it returns a boolean

val animals=arrayListOf<String>()
if(animals.isEmpty()){
	animals.add("dog")
}


some functions you might not expect to return a boolean

val animals=arrayListOf("cat","dog")
if(animals.add("horse")){
	println("Horse was successfully added")
}


Check Kotlinlang.org


Ask a user to input their age.

If they are under 13, they are a child
If they are under 18, they are a teen
If they are older, they are an adult.
Use ranges to print out the correct message.
If the age is 0, convert it to 1.



var input=(readLine()?:"1").toInt()
if(input==0) input=1
val agetype=if (input in 1..12){ "a child"} else if(input in 13..17){ "a teen" } else{ "adult" }
println("user is $agetype")


Section17:
Section Objectives

when checks values, if checks boolean expression
when conditional
when statement(returning a value)
capturing the subject

when(variable){

value1->{
//do something
}

value2->{
//do something
}

value3->{
//do something
}

value4->{
//do something
}

value5->{
//do something
}


}


var action:String
when(animal){
"cat"->{
	action="Pet it"
}

"dog"->{
	action="feed it"
}

else->{
	action="google it"
}

}

println("When you meet a $animal you should $action")

make decisions based on values of a variable or expression

when(numer%2){

0-> result="number is even"
1-> result="number is odd"
}


Inside a when block you can have any code u like including more when statement

when(variable){

val1->{
	//do something
}

val2->{

when(variableb){

	valueB1->{
	
	}
	
	valueb2->{
	
	}
}
}
}

//should be used when return type of all values is of same datatype

var action=when(animal){

"cat"-> "pet it"
"dog"-> "feed it"
else -> "google it"
}


When: Curly braces are not needed if there is only one line of code

val month="January"
val days=when(month){

"January"->31
"February"-> 28
"March"-> 31
else-> 30

}


If two values have the same effect they can be put on the same line, separated by a comma


val month="January"
val days=when(month){
"January","March","May"->31
"February"->28
else->30
}


Capturing the subject:
It's possible to capture the value in a when statement and use it in the block

val name="Michelle"
when(val length=name.length){

in 1..5 -> println("A name with $length character is short")
in 6..10 -> println("A name with $length character is medium")
else -> println("A name with $length character is long")

}

This is useful when getting the result of a function


Practice When condition:
val input=readLine()?:"3"
val meals=input.toInt()

when(meals){

in 0..2 -> println("You should eat more")
3-> println("That's perfect")
else -> println("You should eat less")
}

val input=readLine()?:"0"
val hour=input.toInt()
if(hour>23) hour=23
when(hour){

in 6..11 -> println("morning")
in 12..14 -> println("noon")
in 15..17 -> println("afternoon")
in 18..21 -> println("evening")
in 22..23 -> println("night")
in 0..5 -> println("night")

}

val timeOfDay=when(hour){

in 6..11 -> "morning"
in 12..14 -> "noon"
in 15..17 -> "afternoon"
in 18..21 -> "evening"
else -> "night"
}

println("At $hour:00 it's $timeOfDay")


val name=readLine()?:""

when(name[0]){
'A','B','C'-> println("First letters")
in 'D'..'F'-> println("Middle letters")
else -> println("Rest of the letters")
}




Section18:
For loop
Ranges in for loops
Nested for loops


for(item:String in collection){
//do something
}

val animals=arrayListOf("cat","dog","mouse","bear")
for(animal in animals){
println("Feed the $animal")
}


for(i in 1..12){

val month=when(i){
1->"January"
2->"February"
3->"March"
4->"April"
5->"May"
6->"June"
7->"July"
8->"August"
9->"September"
10->"October"
11->"November"
else ->"December"

}

println("Month #$i is called $month")
}

var total=0
for(i in 1..100){
	total+=i;
}
println("Total is $total")


val customers=hashMapOf(Pair("Alice",4),Pair("Judy",8),Pair("Anna",6))

for(cust in customers.keys){
	val purchases=customers[cust]
	println("$cust you purchased $purchases items")
}


Ask the user to input a year. For each month of that year, print out how many days there are.

Make sure you count leap years.

Assume a leap year is a year that is divisible by 4

val input=readLine()?:"2020"
val year=input.toInt()

for(i in 1..12){

val message=when(i){
1-> "January has 31 days"
2-> if(year%4==0) "February has 29 days" else "February has 28 days"
3-> "March has 31 days"
4-> "April has 30 days"
5-> "May has 31 days"
6-> "June has 30 days"
7-> "July has 31 days"
8-> "August has 31 days"
9-> "September has 30 days"
10-> "October has 31 days"
11-> "November has 30 days"
12 -> "December has 31 days"

}
}


for(i in 1..3){
println("Strike $i")
}
println("you are out")


for(i in 10 downTo 0){

println(i)
when(i){
9-> println("Start your engines")
6-> println("On your marks")
3-> println("Get set")
0-> println("Go!")
}
}

for(i in 10 downTo 0 step3){
println(i)
}
	
	
Nested for loops:
inside a for loop you can have any code you like
including other for loops

for(i in 1..5){

for(j in 1..5){
	print("$i,$j \t")
}
println()
}
	
	
var input=readLine()?:"0"
input=input.toInt()
for(i in input..0){
	if(input%7==0){
		println("$input")
	}

}
	
for(i in 1..10){
for(j in 1..i){
	prinltn("\uD83D\uDE00")
}
println()
}
	
var input=readLine()?:"
var size=input.toInt()
for(i in 1..size){
for(j in 1..size){
	when(i*j%3){
	0-> print("\uD83D\uDE00\t")
	1->print("\uD83E\uDD28\t")
	2->print("\uD83D\uDE31\t")
	}
}
println()
}

	
Section19:
While loop
video179:
Section Objectives

While loops
Do While loops
Nested while loops

while loop:
executes a block of code while a condition is true
var i=0
while(i<10)[

//do something
i++
}


var puzzlePieces=20
var piecesPlaced=0
while(piecesPlaced<puzzlePieces){
piecesPlaced++
}


var i=0
while(i<10){

i++
println("#$i: Hello")
}

var cats=listOf("Tiger","Smokey","Sassy","Patch","Sammy")
var i=0
while(i<cats.size){

println("Hello $cats[i]")
i++;
}

val input=(readLine()?:"0").toInt()
var i=1L
var factorial=1
while(i<=input){
factorial*=i
}

println("$factorial is the factorial of $input")


Exercise: While loop
Ask the user to input a large integer.

Print out all the numbers that are divisible by 7, that are less than the user’s number.


println("Please enter a number")
val input=readLine()?:""
val number=input.toInt()
var i=0
while(i<number){
if(i%7==0)
	println("$i is divisible by 7")
i++
}


video184:
Do while loop:

var i=0
do{
//do something
i++
}while(i<10)



val puzzlePieces=20
val piecesPlaced=0

do{
piecesPlaced++
println("Placed pieces #$piecesPlaced")

}while(piecesPlaced<puzzlePieces)


Nested while loops:
A while loop can block of code can contain anything including other loops:
var i=1
var j=1
while(i<=10){

while(j<=10){
	print("$i,$j\t")
	j++
}
i++
j=0
println()
}



var finished=false
do{

val input=readLine()?:""
var number=input.toInt()
if(number>100){
println("Thanks")
finished=true
}else{
println("$number is not greater than 100, please try again")
}
}while(!finished)



var finished=false
do{
val input=readLine()?:""
var factorial=1
for(int i=1;i<=input.toInt();i++){
factorial*=i
}

if(factorial>3000000){
finished=true
}else{
println("$number!=$factorial is smaller than 3000000. Please try again!")
}
}while(!finished)




Exercise: Do while loop
You have a set of usernames
val usernames = hashSetOf(“john”, “bob”, “alice”)
Ask the user to choose their username. If their username is taken, print out a message and ask again.
Add the username to the set.



val usernames=hashSetOf("raghu","sumanth","bob","alice","john")
var finished=false
do{
println("Please choose your username")
val inputuser=readLine()?:""
if(usernames.contians(inputuser)){

println("$inputuser is taken, please try again")
}else{

	println("$input is your new username")
	finished=true
	usernames.add(inputuser)
}

}while(!finished)

println(usernames)


Section recap:
what while loops are and what they are useful for
check the condition at the end with do while loops
Nested while loops


Section20:
Break and Continue:
Break keyword
Continue keyword
Labels

The break keyword:
Terminates a loop

var onlyEventNumbers=arrayListOf(2,8,4,7,6,9)
for(number in onlyEvenNumbers){

if(number%2 !=0) break
println("Half of ${number/2}")

}

The continue keyword

var onlyEventNumbers=arrayListOf(2,8,4,7,6,9)
for(number in onlyEvenNumbers){

if(number%2 !=0) continue
println("Half of ${number/2}")

}


video193:
Labels
User to mark a position in code that you can jump to
Can be used with break and continue
A label is basically a word followed by @ sign.

loop@for(i in 1..10){
for(j in 1..10){

if(i%3==0) break@loop

println("$i,$j")
}

}


loop@for(i in 1..10){
for(j in 1..10){

if(i%3==0) continue@loop

println("$i,$j")
}

}


An animal shelter is accepting all animals except snake
A user is allowed to bring 5 animals to the shelter
Ask the user to input the animals they want to bring
If they bring a snake, print a message and stop accepting animals


val animals=arrayListOf<String>()
for(i in 1..5){

	println("Please enter an animal")
	val input=readLine()?:""
	if(input == "snake"){
		println("Sorry we cannot accept snakes")
		break
	}
	animals.add(input)
	println("Current animals $animals")
	
}


val clients=arrayListOf("Anna","Bob","Carol","David")

for(client in clients){

if(client[0]=='C') continue
println("Hello $client")
}



Exercise: Break and continue
A group of young people are going to a nightclub.

Design a program that accepts user ages.

The program displays a welcome message for each user.

If it receives an age lower than 18, it prints a message that this client is not allowed.

If it receives the word “stop”, the program ends


var people=arrayListOf()


do{
val user=readLine()?:""
if(user=="stop")
	break;
val userage=(user).toInt
if(userage<18){
	println("Sorry you cannot go in")
	continue;
}
println("Welcome to the club")
}while(true)


Section21:
Functions
Section Objectives:
Functions
Parameters
Returns


What are functions:
A way to group code that can be executed 0 or more times

main is a special function that allows the system to have an entry point in our program.


A function may not get the same result on different runs
Can accept input and return output

create a function
fun functionName(){
//do something

}

call/invoke a function
fun sayHello(){
	println("Hello everyone")
}

for(i in 1..3){
	sayHello()
}


fun printAlphabet(){

println("a,b,c,d,e,f,g,h,i,j,k,l,m,n,o,p,q,r,s,t,u,v,w,x,y,z")
}


var i=5

do{
i--
printAlphabet()

}while(i>0)


video200: Practice Functions
Design a function that prints a hello message
Call it 10 times

//Since we have defined sayHello already in another kotlin file..we can define the same again


fun printHello(){
println("Hello, how are you?")
}

fun main(args:Array<String>){

for(i in 1..10){
	printHello()
}
}

Design a function that asks a user for a number, multiplies that number by 17 and prints out the result

Call the function 3 times

fun multiplyNumber(){

	println("Please enter a number")
	val input=readLine()?:""
	val number=input.toInt()
	println("$number *17=${number*17}")
	
}

fun main(args:Array<String>){
	for(i in 1..3){
		multiplyNumber()
	}
}



Design a function that asks for a user’s name. Then it asks for a user’s birth year.
Finally, it prints out a message saying the user’s name and age.
Call the function 3 times.

fun main(args:Array<String>){
for( i in 1..3){
	askDetails()
}
}

fun askDetails(){

println("Please enter user name")
val username=readLine()?:""
println("please enter user birth year")
val birthyear=readLine()?""

println("User's name: ${name} and age:${2021-birthyear.toInt()-1} or ${2021-birthyear.toInt()}")
}


video203:
Function Parameters:

A functioin can accept parameters(arguments)
Parameters influence how a function behaves and what the outcome of the function is.

fun double(number:Int){
	println("Double of $number is ${number*2}")
}

fun main(args:Array<String>){
	double(5)
	for(i in 1..10){
		double(i)
	}
}


fun sayHello(people:Collection<String>){
	for(person in people){
		println("Hi $person")
	}
}

fun main(args:Array<String>){
	val people=listOf("Anna","Bob","Carol")
	sayHello(people)
}



Parameters can have default value
fun double(number:Int,message:String="Double is"){
	println("$message ${number*2}")
}

fun main(args:Array<String>){
	double(5,"5*5=")
}



video204: Function Return
A function can return a result

fun calculateCircleArea(radius:Int):Double{

val pi=3.1415
return pi*radius*radius

}


val r=24
println("A circle with a radius of $r has an area of ${calculateCircleArea(r)}")



fun  main(args:Array<String>){

val r=10
val area=calculateCircleArea(r)
println("A circle with the radius $r has an area of $area")

}



fun personalisedGreeting(person:String):String{

val  greeting=when(person[0]){
	'A'-> "Are you ok $person"
	'W' -> "What's up $person"
	else -> "Hi $person"
}
	return greeting
}

val clients=listOf("Anna","Bob","William")
for(client in clients){
	val greetin=personalisedGreeting(client)
	println(greeting)
}


val people=listOf("Anna","Bob","William")
for(person in people){

val message=personalisedGreeting(people)
println(message)
}


Return shorthand:
fun calculateCircleArea(radius:Int):Int{
	val pi=3.1415
	return pi*radius*
}


fun calculateCircleArea(radius:Int)=3.1415*radius*radius

val r=24
println("A circle with a radius of $r has an area of ${calculateCircleArea(r)}")


More Functions
Create a function that receives 2 parameters and return the sum of those parameters
Call the function 3 times and display the result


fun addition(p1:Int,p2:Int):Int{
	return p1+p2
}

fun main(args:Array<String>){
	for(i in 1..3){
		println(addition(i*5,i*9))
	}	
}

Create a function that receives the price of a product, add 20% tax and return the result
These are the products in your online store
val products=hashMapOf(Pair("shoes",29.99),Pair("socks",5.99),Pair("jeans",39.99))
Print out the final price for each product

fun addTax(price:Double?)=price?.times(1.2)

fun main(args:Array<String>){
val products=hashMapOf(Pair("shoes",29.99),Pair("socks",5.99),Pair("jeans",39.99))

for(item in products.keys){
	val finalPrice=addTax(products[item])
	println("$item cost $finalPrice")
}



Create a function that receives the name of an animal, and returns the estimated lifespan.

cats -> 15
dogs -> 10
rabbit -> 12
everything else -> 20

Ask the user to input an animal, then print out the estimated lifespan for that animal.



val lifespan=hashMapOf(Pair("cats",15),Pair("dogs",10),Pair("rabbit",12))

fun getLifespan(animal:String){
	
	val lifespan =when(animal){
				"cats"-> 15
				"dogs"->10
				"rabbit"->12
				else-> 20
	}
	return lifespan
}	
	
fun main(args:Array<String>){

println("Please enter an animal")
val animal=readLine()?:"
val lifespan=getLifespan(animal)
println("A $animal has a lifespan of $lifespan years")

}




Section 22: Functions Continued
Section Objectives
Function Overloading
Scope
Vararg
Local functions


video 210:
Overloading
Two functions can have the same name
if they have the different numbers or types of parameters

fun multiply(number:Int)=number*2
fun multiply(number:Int,multiplier:Int)=number*multiplier

multiply(3)
multiply(3,5)

Two functions can have the same name 
if they have different number or type of parameters

multiply(3)
multiply(3,5)
multiply(3,5.5)

fun sayHello(person:String){

println("Hi $person")

}

fun sayHello(person:Collection<String>){

for(person in people){
	println("Hi $person")
}
}

sayHello("John")
sayHello(listOf("Anna","Bob","Carol"))


Create an overloaded function that takes either an animal or a list of animals

It then prints out a message to feed each animal

fun feedAnimal(animal:String){

println("Feeding the $animal")

}


fun feedAnimal(animals:Collection<String>){

for(animal in animals){
	feedAnimal(animal)
}
}

fun main(args:Array<String>){

feedAnimal("cat")
feedAnimal(setOf("cat","dog","cow"))

}


create a function that takes a message and prints out the size of the message.
Overload the function to take an integer and print out a string of the size of that integer. The content of the string is not important

fun printSize(message:String){
	println("$message has a size of ${message.length}")
}

fun printSize(number:Int){
var message=""
for (i in 1..number){
	message+="a"
}
	println("A message of $number is $message")
}


printSize("Hello how are you")
printSize(8)



Exercise: Overloading
Create a function that takes a product name and price. It adds 20% tax to that product and displays a message saying how much the product costs.

Overload the function so that it takes a map of products and prices, and does the same thing.

Call both functions in your program.



fun cost(name:String,price:Double?){

val totalcost=price?.times(1.2)
println("Total cost of $product is $totalcost")

}

fun cost(products:Map<String,Double>){

for( product in products.keys){
	cost(product,products[product])
}
}

fun main(args:Array<String>){
	cost("coffee",4.99)
	val products=mapOf(Pair("cake",3.99),Pair("can of soda",1.5))
	cost(products)
}



video214 Scope:

basically means visibility of functions, variables, alot of other stuff
deaply related to OOPs.
A variable defined inside a function only exists in that function

when execution exits from the function the variable is destroyed and memory is freedup and there is no way to get information unless we pass that info through return of that function and get the data to outside of the function.

Variables defined in a function are only available, visibile and accessible in that function.

fun example(){

val flowers=5
println("I have $flowers flowers ")
}




video218:
Vararg

Variable number of parameters(arguments)

fun sayHello(vararg names:String){
for(name in names){
	println("Hello $name")
}
}

sayHello("Mary","John","Alex")



video219:
Practive varargs:

fun sum(varargs nums:Int):Int{

 var sum=0
for( num in nums){
	sum+=num
}
return sum
}


println(sum(4,5,6,7,8,9))
println(sum(1,2,3,4,65,7))
println(sum(1,2,6,5,4,32,7,9))


Exercise: Vararg
Create a function that takes an integer variable “count” and a variable number of client names. Print out “count” hello messages for each client.

i.e. if count = 3, print out 3 hello messages for each client.


fun testfun(count:Int, varargs names:String){

for(name in names){
for( i in 1..count){
print("hello $name-")
}
println()
}
}



Functions- Local functions
A local function is a function inside a function


inner function will be accessible only inside the context of outside function

fun listAnimals(){

fun listOneAnimal(animal:String){

println("I have a $animal")
}
val myAnimals=arrayListOf("cat","dog","cow","horse")
for(animal in myAnimals){
	listOneAnimal(animal)
}
}




Create a function that takes a map of users and their bank balance.
Inside create a function that takes a number and returns its double

Double each user's bank balance and print out a statement


fun awesomeBank(users:HashMap<String,Double?>){

fun doubleAmount(amount:Double?)=amount?.times(2)

for(user in users.keys){
	users[user]=doubleAmount(users[user])
}

println(users)

}

fun main(args:Array<String>){

	awesomeBank(hashMapOf(Pair("Alice",546.0),Pair("Bob",345.0),Pair("Carol",456.0)));
}


Exercise: Local functions
Create a function that asks the user for a name until an empty string is introduced.

Create a local function that takes a name and prints a greeting.

For each name introduced, print out a greeting.



fun printGreeting(){

fun sayHi(name:String){
	println("Hi $name how are you?")
	
}
while(true){

println("Please enter a name")
val name=readLine()?:""
if(name=="") break

sayHi(name)

}	
}

Section Recap:
Overloading - declaring multiple functions with the same name
Scope- variable access
Vararg - declaring varying number of input parameters
Local functions- functions inside functions




Section23:
Lambda functions

Functions that don't have a name
we can call them as anonymous functions

we can use this functions to pass as parameters to other functions
These other functions that receive these functions are called Higher order functions

Section Objectives:
Lambdas
Higher order functions

Lambdas:
A lambda is an anonymous function that has no name

fun printMessage(name:String){
	println("Hello $name")
}

(name:String-> println("Hello $name"))


A lambda function can have parameters they are declared at the start of the block

A lambda function can be assigned to a variable
val myLambda:(String)->Unit=(name:String-> println("Hello $name"))


this variable can be passed as a parameter to a new function also known as higher order function


video229:
Higher order function

A HOF is a function that takes another function as a parameter

fun sayHello(names:ArrayList<String>,doSomething:(String)->Unit){

for(name in names){
	doSomething(name)
}
}



val myLambda={name:String->println("Hello $name")}


val names=arrayListOf("Mary","Kate","Mike")
sayHello(names,myLambda)


A HOF is a function that takes another function as a parameter

sayHello(names){name:String->println("Hello $name")}



Lambda and HOFs:
Create a Higher Order function that takes a mutable collection of integers and a lambda function. It then applies the lambda function to every even element of that collection

Create a lambda function that when applied to an integer, it returns that integer divided by 10

Call the HOF using your lambda and display the result


fun update(numbers:ArrayList<Int>,lbd:(Int)->Int):ArrayList<Int>{


for(i in 0..numbers.size-1){
	if(numers[i]%2==0)
		numers[i]=lbd(numbers[i])
		
}
return numbers
}


fun main(args:Array<String>){
val numbers=arrayListOf(3,623,7,5,41,32,23,435)
prinltn(numbers)
val newNumbers=update(numbers){number->number/10}
println(newNumbers)
}



Exercise: Lambdas and Higher Order Functions
Create a Higher Order Function that takes a list of client names and a lambda expression that returns a String.

It then applies the lambda expression to every client name, creates a new collection of the results and returns the result.

Create a lambda expression that takes a client name String and returns a personalised message.

Call the HOF and print out the result.

fun getMessages(clients:Collection<String>,getMessage:(String)->String):ArrayList<String>{


val messages=arrayListOf<String>()
for(client in clients){
	messages.add(getMessage(client))
}
return messages
}


fun main(args:Array<String>){
	val clients=arrayListOf("Micheal","Jane","Dan","Michelle")
	val messages=getMessages(clients){name->"Hello $name, how are you"}
	println(clients)
	println(messages)
	
	for(i in 0..clients.size-1){
		println("Message for ${clients[i]}")
		println(messages[i])
		println()
	}
	
}


Common HOFs

forEach:
val clients=listOf("Anna","Bob","Carol","David")
clients.forEach{println("Hello $it")}


***
If a lambda has a single parameter then we refer that parameter as it


filter:
val clients=listOf("Anna","Bob","Carol","David")

clients.filter{it.length<5}
		.forEach{println("Hello $it")}


map: creates a new collection based on the predicate or value of lambda we provide

val sizes=clients.map{it.length}
println(sizes)


sortedBy:
val sorted=clients.sortedBy{it.length}
println(clients)

maxBy:
val max=clients.maxBy(it.length)
println(max)

minBy:
val min=clients.minBy(it.length)
println(min)


video234: Practice: Common Higer Order Functions


Given a set of random integers, print out a subset that consists only of double digit integers

fun main(args:Array<String>){

val numbers=setOf(2,3,4,2,2,1,2,3,33,4)
println(numbers.filter{it>=10 && it<100})


}


You have a list of clients from your online store.
Display a list that is sorted by the last letter of their name

fun main(args:Array<String>){

val clients=listOf("Job","Bob","test","Arun","Krish","Soumya")
println(client.sortedBy{it[it-length-1]})
}


Given a list of 3 digit integers
Printout the integer that has the biggest middle digit

val ints=listOf(345,234,466,678,787,968,777)
println(ints.maxBy{it.toString()[1].toInt()})

println(ints.maxBy{it/10%10})



Exercise: Common Higher Order Functions
Given a collection of random integers.

If a number is odd, double it.

If a number is even, half it.

Print out a subset of the collection that has numbers greater than 25.


val ints=listOf(3,2,4,6,7,9,8)

println(ints.map({if(it%2==0){it/2} else {it*2}}).filter(it>25))



video237: Section Recap



Section 24: Packages
video238: Section Objectives

the way to structure your code so that u can have certain portions of your code available to some parts and hide them from other parts of your code


Packages
Naming Convention
Imports


video239: Packages
visibility or scope


Scope related to variables or functions

A function inside a file can have access to  other functions in other files or it may not have access
this is called scope of a file

We influence scope of the file with packages

We will learn more and more about packages as we go through our course

A package is a way to group related code together
Files, Functions and Classes are part of packages

Package defination is first line of the file

a package is a folder on the disk




package com.organisation.coolfeature
package com.different.organisation



fun buildCoolFeature(){
	println("Building a cool feature for our project")

}

Scope(Visibility) withi the same package
In order to use code from another package, that package must be imported into the project

Files inside the package will have access to functionality within the package



video240:
Naming Convention

Package names are separated by dot
Names are always lowercase with no underscores
Leftmost name is the highest level package
Rightmost name is the lowest level package

com.organisation.project.custompackagename




video241: Imports
In order to use code from another package, that code must be imported into the project
imports go at the top of the file, after the package declaration

fun hi(){

println("Hello How are you?")
}

Create three packages

com.exercise.hello
    Create a function sayHi that takes a client name and prints a hello message.

com.exercise.client
    Create a function getName that reads a client name, then uses the sayHi function to print a hello message.

com.exercise.run
    Call the getName function.
	
	

Declare packages and restrict code visibility
	

Section25:
Project Hungman

you have to guess a word letter by letter
you have 6 guesses
For every mistake, more of the man is drawn

if the whole man is drawn, he is hanged and game over

if the word is guessed, the man is spared

video247:
Creating the project



video249:
Starting Position

video250:
Game Algorithm:


Section26:
Project Tic Tac Toe
video252:

video254:
Play move



Section27: Object Oriented Programming

is a way to think about programs in a way that makes them more easy to develop

it relies on what we learnt so far, it leaverages to build structures in our program that is being used later on to achieve our objective in an easy way.


Objectives of this section:
What is OOP
Classes
Objects
Creating classes and objects
Inheritance



what is OOP:
Start
Retrieve data from web
Convert data
Print data to screen
Finish


Start
Coordinator->
|Data Convertor
|Screen Manager
|Webdata manager
|Database data manager
|Print manager
|Finish

entities/object or group of objects

OOP is a different paradigm
We think of entities in a program that perform certain tasks
The tasks are completely contained in the object(encapsulation)

The entities can be replaced with similar entities that perform the same task in a different way



classes:
blue print for a component(Object)
class Car{

var model:String? =null
var topSpeed=100

fun start(){

println("Start the $model")
}

fun drive(speed:Int){
	println("Driving at a speed of $speed")
}

}



video262:
Objects

an object is an instance of a class
val myCar=Car()
val yourCar=Car()

An Object can change its value without impacting other objects from the same class
myCar.model="BMW"
yourCar.model="Toyota"


An object can call its method

video:263

class Animal{

var name=""
var topSpeed=0
fun run(){
	println("$name's top speed is $topSpeed")
	
}
}

fun main(args:Array<String>){

var cat=Animal()
cat.run()
cat.name="Cat"
cat.topSpeed=40
cat.run()

}



class Math{
	fun add(a:Int,b:Int)=a+b
	fun sub(a:Int,b:Int)=a-b
	fun mul(a:Int,b:Int)=a*b
	fun div(a:Int,b:Int)=a/4
	fun mod(a:Int,b:Int)=a%b
}

fun main(args:Array<String>){
	val math=Math()
	math.add(10,20)
	math.sub(10,20)
	math.mul(10,20)
	math.div(20,10)
	math.mod(20,7)
}


class JetPack{
var elevation=0
fun burn(seconds:Int){
	elevation+=seconds
}
fun stop(seconds:Int){
	elevation-=3*seconds
	if(elevation<0){ elevation=0}
	
}
}

fun main(args:Array<String>){

val jetpack=JetPack()
jetpack.burn(10)
println("User height is ${jetpack.elevation}")
jetpack.stop(2)
println("User height is ${jetpack.elevation}")
jetpack.burn(4)
println("User height is ${jetpack.elevation}")
jetpack.stop(4)
println("User height is ${jetpack.elevation}")


}



class Calculator{

var total=0.

fun add(num:Double){
	total+=num
}

fun sub(num:Double){
	total-=num
}

fun mul(num:Double){
	total*=num
}

fun div(num:Double){
	total/=num
}

fun reset(){
	total=0.0
}
}

fun main(args:Array<String>){

val calci=Calculator()
println("Total value of calculator: ${calci.total})
calci.add(10)
println("Total value of calculator: ${calci.total})
calci.sub(5)
println("Total value of calculator: ${calci.total})
calci.mul(5)
println("Total value of calculator: ${calci.total})
calci.div(5)
println("Total value of calculator: ${calci.total})
calci.reset()
println("Total value of calculator: ${calci.total})

}


The object construct
A class can be instantiated, the instance is called an object
An object is a static class, all methods and variables can be accessed without an instance

Singleton: one instance of a class

The object construct in kotlin basically allows us to create singleton's in an easy way


object DatabaseAccess{

var connected=false
fun connect(){
	connected=true
	println("Connected to database")
}

fun disconnect(){

	connected=false
	println("Disconnected from database")
}
}

DatabaseAccess.connect()
println("Database connected: ${DatabaseAccess.connected}")


video269:
Classes and Objects
Kotlin is a language that is built on top of java, 
In kotlin everything is an object
String,Int,Float,Boolean, ArrayList,HashMap 
All variable types are objects
Collection, List are interfaces(more on that later), they are sort of object


val animal=listOf("cat","dog","horse")
animal.size
animal.get(0)

Object definations(classes) can contain references to other objects

class Table{
	val color:String="White"
}

val table=Table()
println("Color: ${table.color}")


class Car{

fun drive(){
	println("Driving along in my car")
}
}

class Garage{
	val car=Car()
}

fun main(args:Array<String>){
	val myGarage=Garage()
	myGarage.car.drive()
}

video270: Inheritance

We can apply the variables and methods of a class to another class

we can get benefit of code reusability
Inorder to allow other classes to inherit from a class we have to declare it with open, that means parent class should be started with open 

Child class name and parent class name should be separeted by : instead of extends as we use in java

open class Dog{

var size:Int=0

fun bark(){
	println("Bark")
}

fun play(){
	println("Playing")
}


}

class Corgi: Dog(){

}

fun main(args:Array<String>){
	val myDoggy=Corgi()
	myDoggy.size=10
	println(myDoggy.size)
	myDoggy.bark()
	myDoggy.play()
}

Inheritance is transitive:
Corgi class has access to the methods and variables in Dog and Animal

Animal
 |
Dog
 |
Corgi



video271:


open class Laptop{
var screenSize=15
var speed=1200
var name="Generic laptop"

fun run(){
	println("running $name laptop with size $screenSize and speed $speed")
	
}



}

class Apple:Laptop(){

}

fun main(args:Array<String>){

val laptop= Laptop()
val apple= Apple()
apple.screenSize=12
apple.name="Apple Macbook"
laptop.run()
apple.run()
}


video272:

open class Airplane{
var name="Generic Airplane"
var speed=0.0
var altitude=0.0

fun ascend(deltaAlt:Double){
	altitude+=deltaAlt
	println("$name has an altitude of $altitude and speed $speed")
}

fun descend(deltaAlt:Double){
altitude-=deltaAlt
	println("$name has an altitude of $altitude and speed $speed")
}

}

class Boeing:Airplane(){

}

class Airbus:Airplane(){

}

fun main(args:Array<String>){

val boeing737=Boeing()
val a320=Airbus()
boeing737.speed=700
a320.speed=800

boeing737.name="Boeing 737"
a320.name="Airbus a320"

boeing737.ascend(1000)
a320.ascend(1000)
boeing737.descend(200)
a320.descend(200)
boeing737.ascend(2000)
a320.descend(200)
a320.descend(320)


}




class Job{

var name="Generic Job"
var revenue=0.0
var salary=10000.0

fun work(){
	revenue+=salary
	
	println("Job: $name with revenue $revenue and salary $salary")
}

fun study(){
	salary+=1000
	println("Job: $name with revenue $revenue and salary $salary")
}


}

class Engineer:Job(){

}

class Doctor:Job(){

}


fun main(args:Array<String>){


val eng=Engineer()
val doc=Doctor()
eng.name="Engineer"
doc.name="Doctor"

eng.salary=15000
doc.salary=30000

eng.study()
eng.work()
doc.study()
doc.work()
doc.study()
doc.study()
doc.study()
doc.work()
eng.study()
eng.work()
eng.study()
eng.study()
eng.study()
eng.work()

}




section28:
More about classes
video276  Section Objectives

Constructors
Getters and Setters
The this keyword
The init block
The Companion object


Constructors:
Defines a set of variables that are available at the creation of an object
//If we have only one constructor we will keep parameters at the //class defination itself similar to how a function works

class Car(var model:String,var topSpeed:Int){

}


val myCar=Car("BMW",220)

A class can have multiple ways of being created

class Car{

constructor(){
model="No Model"
topSpeed=150
}

constructor(newModel:String){
model=newModel
topSpeed=150
}

constructor(newModel:String,newSpeed: Int){
model=newModel
topSpeed=newSpeed
}

var model:String?=null
var topSpeed=100


}


val myCar=Car()
val myCar=Car("BMW")
val hisCar=Car("Fiat",220)


When we need only one constructor then we don't need to define the constructor explicitly


class Table{

var legs=4
var height=3

constructor(){
	legs=0
	height=1
	
}


constructor(newLegs:Int){
	legs=newLegs
	height=1
	
}


constructor(newLegs:Int,newHeight:Int){
	legs=newLegs
	height=newHeight
	
}

fun printInfo(){
	println("This table has legs: $legs and a height of $height") 
}

}

fun main(args:Array<String>){

val table1=Table()
val table2=Table(2)
val table3=Table(10,30)

table1.printInfo()
table2.printInfo()
table3.printInfo()


}



class UserAccount{
	var userName="Dummy Name"
	var balance=3000.0
	
	constructor(){
		userName="UserName dummy"
		balance=0.0
		canAfford()
	}
	
	val tshirtPrice=20
	fun canAfford(){
	
	if(balance>tshirtPrice){
		println("$userName can afford ${balance/tshirtPrice} tshirts")
	}else{
		println("$userName cannot afford any tshirts")
	}	
	}
	
	constructor(name:String){
		userName=name
		balance=accBalance
		canAfford()
	}
	
	
	constructor(name:String,accBalance:Double){
		userName=name
		balance=accBalance
		canAfford()
	}
	
	
}


Getters and Setters
Allow us to change the way variables are assigned and retrieved

var customerInfo:Int

get()  //do something
set(value){
 //do something
}



fun main(args:Array<String>){

val myCar=Car()
myCar.speed=100
println("myCar name : ${myCar.name}")
println("myCar speed: ${myCar.speed}")
}

class Car{

var name=""
var speed:Int
get()=50
set(value){
	name="High speed car $value"
}
}


video282: Practice Getters and Setters

class BankAccount{

	var creditRating=500
	var account:Int=0
	get()=field
	set(value){
		if(value>account){
			creditRating++
		}else{
			creditRating--
		}
		field=value
		println("New Credit Rating is $creditRating")
	}
}



fun main(args:Array<String>){

val account=BankAccount()
account.account=300
account.account=400
account.account=100


}


//what is the use purpose of field



video283:

class BankInterest{

var interestRate=0.0
var balance:Int=999
get()=field
set(value){
if(value<1000)
	interestRate=1.0
else if(value<10000)
	interestRate=0.5
else
	interestRate=0.2
field= value
println("The client has $value and has an interest rate of $interestRate")
}

}


fun main(args:Array<String>){

val account=BankInterest()
account.amout=5000
account.amount=500000
account.amount=500
account.amount=1500
account.amount=11500
}



video285:
The this keyword
the "this" keyword refers to parameters of the class

class PostItNote(){

	var message:String="No Message"
	
	fun updateMessage(message:String){
		this.message=message
	}
	
	fun printMessage(){
		println(this.message)
	}
}


val postIt=PostItNote()
println(postIt.message)
postIt.updateMessage("Meeting at 5")
println(postIt.message)



video286: Practice: the This keyword

class Box{

var contents:String=""
fun updateContents(contents:String)[
	this.contents=contents
}

}

fun main(args:Array<String>){
	val myBox=Box()
	println("Contents is: ${myBox.contents}")
	myBox.updateContents("Jewellery")
	println("Contents is: ${myBox.contents}")
	
}


class Table{

var height=4
var size=6

fun update(height:Int,size:Int){
	this.height=height
	this.size=size
}
}

fun main(args:Array<String>){
	val myTable=Table()
	println("Contents is: ${mytable.height} ${mytable.size}")
	myTable.update(10,20)
	println("Contents is: ${mytable.height} ${mytable.size}")
	
}


video289:
The init block

the init block is a component of the class that runs before any other code in the class 



class Car{


var model:String?="no model"
var topSpeed=100

init{
	println("Model $model top speed is $topSpeed")
}

}

fun main(args:Array<String>){

val myCar=Car()
}

The init block provides functionality in addition to the primary constructor


video290: Practice: The init block

class Laptop(val operatingSystem:String){

init{
println("Operating System $operatingSystem is being installed")
}

}

fun main(args:Array<String>){

val laptop=new Laptop("Windows 10")


}



class WebBrowser{

init{
	println("Web browser is connecting")
	println("http://www.google.com/")
}


}

fun main(args:Array<String>){
	val browser=new WebBrowser()
}

video293: The Companion Object
it is a way to make the code available from a class without the need of the object, we called it as static code. We call it static code because we can access it whether or not we have an object, whether or not we have state for that object, we call it as static because we can call it, we can access it directly through the class. it basically makes class code available without the need for an object. 


class Car{

	companion object{
		fun getDrivingInstructions():String{
			return "Drive safe"
		}
	}
}

println(Car.getDrivingInstructions())

Companion object is a non-class related functionality, 




class KotlinCourse{

companion object{
	fun getCourseMetaInfo(){
		println("Kotlin is not a difficult language to learn")
	}
	}
	fun getCourseInfo(){
		println("Kotlin is a Java based development language")
	}
}

fun main(args:Arrray<String>){
val course=KotlinCourse()
course.getCourseInfo()
KotlinCourse.getCourseMetaInfo()


video298:

class Lock(key:Key){
val secretCode:String
init{
	secretCode=generateSecret()
	key.secretCode=secretCode
}

companion object{
fun crateKey()=Key()
}	

fun generateSecret():String{
	return  kotlin.random.Random(System.currentTimeMillis()).nextInt()
}

fun unlock(key:Key){

	if(key.secretCode==secretCode)
		println("Lock is open")
	else:
		println("Key is mandatory")		
}
}
class Key(){
var secretCode:String=""
set(value){
	if(field=="")
		field=value
}
}


fun main(args:Array<String>){

	val correctKey=Lock.createKey()
	val myLock=Lock(correctKey)
	myLock.unlock(correctKey)
	
	val randomKey=Lock.createKey()
	myLock.unlock(randomKey)
	
}

fun main(args:Array<String>){

	val myBook=Book(Book.getEditor())
	println("myBook.editor.editorName)
}

class Book(val editor:Editor){

companion object{
fun getEditor()=Editor("O' Reilly")
}
}

class Eidtor(val editorName:String){

}


section20:
Principles of OOP:
Inheritance
Encapsulation
Abstraction
Polymorphism

Set of guidelines that make a language OO
makes programs scalable, maintainable, easily debugable and understandable
Helps to structure the program into components

Inheritance:
Classes can inherit methods and parameters from other class

Encapsulation:
Hiding data and inner workings of a class from other classes that don't need to know how something is done


Abstraction:
A common feature of 2 classes should be abstracted in a third class

Ploymorphism:
same name many forms

A class can inherit variables and methods from another class
To make a class inheritable, use the open keyword

open class Mom{

	val hairColor="brown"
	val eyeColor="blue"
	
	fun say(message:String){
		println("mom says $message")
	}
}

class Daugher:Mom(){

}

val carol=Daugher()
println(carol.hairColor)
carol.say("Hi")

If a class has multiple constructors, atleast one must be initialized

open class Mom(nativeTongue:String){

	val hairColor="brown"
	val eyeColor="blue"
	
	fun say(message:String){
		println("mom says $message")
	}
}

class Daugher(nativeTongue:String):Mom(nativeTongue){

}

val carol=Daughter("french")
println(carol.hairColor)
carol.say("Hi)


Daugheter classes can override variables in mother classes by creating a variable of the same name

Daughter classes can override methods in mother classes using the override keyword if they are marked as open

open class Mom(nativeTongue:String){

open val hairColor="brown"
val eyecolor="blue"

open fun say(message:String){
	println("Mom says $message")
}	
}


class Daughter(nativeTongue:String):Mom(nativeTongue){

override val hairColor="blonde"
override fun say(message:String){
	println("daughter says $message")
}
}


val carol=Daughter("french")
println(carol.hairColor)
carol.say("Hi")


Daughter classes can access mother class methods and variables using the super keyword



open class Mom(nativeTongue:String){

open val hairColor="brown"
val eyecolor="blue"

open fun say(message:String){
	println("Mom says $message")
}	
}


class Daughter(nativeTongue:String):Mom(nativeTongue){

override val hairColor="blonde"
override fun say(message:String){
	println("daughter says $message")
	super.say(message)
	prntln(super.hairColor)
}
}


video302:

open class Bird{

open val color="grey"
open val speed=50

open fun fly(){
	println("A $color bird can fly upto speed $speed kmph")
}
}

class Parakeet:Bird(){

override val color="green"
override val speed=65

override fun fly(){
	super.fly()
	println("A ${super.color} bird can fly upto speed ${super.speed} kmph")
}
}


val myParakeet=Parakeet()
myParakeet.fly()



video303:


open class Father{

	open val firstName="John"
	val lastName="Smith"
	
	open fun printName(){
		println("My name is $firstName $lastName")
	}
}

class Son:Father(){

override val firstname="Michael"

override fun printName(){
	super.printName()
	println("My father's name is ${super.firstName}  ${super.lastName}")
}
}



fun main(args:Array<String>){

	val me=Son()
	me.printName()
}



video305: Encapsulation and scope

Variables and functions are available only in the block of code they are declared in

Classes can change the scope of their variables/functions

Modifiers:
private- visible inside the class only
proctected: visibile inside class and inheriting class
internal: visible inside package
public: visible to anyone accessing the class


Default is public

open class Airplane{

	var type="Airbus"
	
	fun fly(){
		println("flying")
	}
}

class MyAirplane:Airplane(){


	fun takeoff(){
		println(type)
		fly()
	}
}


class MyCar{
	fun start(){
		val airplane=Airplane()
		println(airplane.type)
		airplane.fly()
	}
}


-----------------

open class Airplane{

	private var type="Airbus"
	
	private fun fly(){
		println("flying")
	}
}

class MyAirplane:Airplane(){


	fun takeoff(){
		println(type)//error not visible
		fly() //error not visible
	}
}


class MyCar{
	fun start(){
		val airplane=Airplane()
		println(airplane.type) //error not visible
		airplane.fly() //error not visible
	}
}


-----------------

open class Airplane{

	protected var type="Airbus"
	
	protected fun fly(){
		println("flying")
	}
}

class MyAirplane:Airplane(){


	fun takeoff(){
		println(type) //executes
		fly() //executes
	}
}


class MyCar{
	fun start(){
		val airplane=Airplane()
		println(airplane.type) //error not accessible
		airplane.fly() //error not accessible
	}
}


--------------------------


open class Airplane{

	internal var type="Airbus"
	
	internal fun fly(){
		println("flying")
	}
}

class MyAirplane:Airplane(){


	fun takeoff(){
		println(type) //executes
		fly()  //executes
	}
}


class MyCar{
	fun start(){
		val airplane=Airplane()
		println(airplane.type) //executes if in same package
		airplane.fly() //executes if in same package
	}
}


Encapsulation is the principle of hiding internal workings of a class

Only show what the others classes need

class Airplane{

protected var type="Airbus"

public fun fly(){
	runEngines()
	println("Flying")
}

	private fun runEngines(){
		//turn on engines
	}
}



------------------

class EncriptionLock(private val privateKey:Int){


	fun unlock(publicKey:Int)= formula(publicKey)==privateKey
	
	
	private fun formula(publicKey:Int)=publicKey/2+5
	
	
	
	
}


val myLock=EncriptionLock(40)
println("Does the key 34 unlock my lock: ${myLock.unlock(34)}")
println("Does the key 45 unlock my lock: ${myLock.unlock(45)}")
println("Does the key 70 unlock my lock: ${myLock.unlock(70)}")
println("Does the key 89 unlock my lock: ${myLock.unlock(89)}")
println("Does the key 136 unlock my lock: ${myLock.unlock(136)}")


----

open class OriginalRestaurant{

protected fun applyFormula():String{
	return "Prepare burgers with lover and care"
}
}


class Franchise: OriginalRestaurant(){


	fun prepareBurgers(){
		println("Preparing burgers according to the secret formula")
		println(applyFormula())
		
		
	}
}


val myRestaurant=Franchise()
myRestaurant.prepareBurgers()



video309: Abstraction
Functionality that is not associated with an instance(object) should be abstracted away

In practice:
If 2 classes share common features, create a super class that contains the common features and inherit from it

Use Interfaces(future section)

The keyword abstract means class cannot be instantiated only extended from

ex:

class Bottle{

fun pour(){
	println("Pouring liquid")
}
}

class Jug{

fun pour(){
	println("pouring liquid")
}
}


----

abstract class Container{

fun pour(){
	println("pouring liquid")
}
}


class Bottle : Container(){

fun fill(){
	println("filling bottle")
}	
}

class Jug:Container(){

}


fun main(args:Array<String>){

val container:Container=Bottle()
container.fill()//error

val container1=Bottle()
container1.fill() //no error


}


abstract class Container{

abstract fun pour()
}

class Bottle:Container{

override fun pour(){

	println("Poring bottle")
}
}


class Jug:Container(){

override fun pour(){

	println("Pouring jug")
}
}



Reduces code duplication
Structured code based on real world concepts 
Both bootle and jug are containers
Helps remove irrelevant code and puts it in a separate class



abstract class Dog(name:String){


abstract fun run()
abstract fun bark()
abstract fun play()
}

class pug(name:String):Dog(name){
override fun run(){
	println("A $name can run")
}

override fun bark(){
println("A $name Cannot bark")
}
override fun play(){
println("A $name can play")
}


}


class BassetHound(val name:String):Dog(name){


override fun run(){
	println("A $name cannot run")
}

override fun bark(){
println("A $name can bark")
}
override fun play(){
println("A $name can play")
}

}



class Chihuahua(val name:String):Dog(name){


override fun run(){
	println("A $name can run")
}

override fun bark(){
println("A $name definately bark")
}
override fun play(){
println("A $name cannot play")
}

}


val myDog:Dog=Pug("pug")
val yourDog:Dog=BassetHound("Basset Hound")
val hisDog:Dog=Chihuahua("chihuahua")


myDog.play()
yourDog.play()
hisDog.play()


myDog.run()
yourDog.run()
hisDog.run()


myDog.bark()
yourDog.bark()
hisDog.bark()


abstract class DefaultOven{

	val cookingspeed=120
	open val averageTemperate=180
	
	abstract fun cooking()

}



class Bosch:DefaultOven(){

override val averageTemperature=210
override fun cooking(){
	println("Bosch oven is cooking in $cookingSpeed seconds at $averageTemperature temperature")
}
}


class Roster:DefaultOven(){


override fun cooking(){
	println("A roaster roasts at $cookingSpeed seconds at $averageTemperature temperature")
}

}


val myOven:DefaultOven=Bosch()
val myRoaster:DefaultOven=Roaster()

myOven.cooking()
myRoaster.cooking()



video313:
Polymorphism
one name many forms

A method/function can do different things in different situations

2 types:
Dynamic: method overriding
Static: Method overloading


open class Mom(){

open fun say(message:String){
	println("Mom says $message")
}
}

class Daugher:Mom(){
override fun say(message:String){

	println("daughter says $message")
}
}



Method Overloading:
class Mom(){


fun say(message:String){
	println("mom says $message")
	
}

fun say(){
	println("mom says hi")
}

fun say(message:String,times:Int){
	
	for(i in 1..times){
		println(message)
		
	}
}

fun say(times:Int){
	for(i in 1..times){
		println(" Mom says hello")
	}
}
}


val mom=Mom()
val daugher=Daughter()
daughter.say("hi")
mom.say("hi")
mom.say()
mom.say(4)
mom.say("hello daughter",2)


Method: Overloading:
amount and type of parameters are important

-------------

class Translator{

fun sayHello(){
	println("English: Hello")
}

fun sayHello(language:String){
	when(language){
		"fr"-> println("French:Bonjour!")
		"ch"-> println("Chinese: Ni hoo!")
		else -> println("English: hello")
	}
}
}

val transulator=Translator()
translator.sayHello()
translator.sayHello("ch")
translator.sayHello("fr")
translator.sayHello("de")




A TV can provide programs from a certain channel.

It can also provide channel and subtitle information.

It can also provide programs that were shown at a certain time of the day.

Implement this in a program and call the various methods.


class TV{
fun getChannel(id:String){
	println("Regular broadcast for channel $id")
	
	
}

fun getChannel(id:String,subtitles:Boolean){
	println("Regular broadcast for channel $id")
	if(subtitles)
		println("with subtitles")
	else
		println("without subtitles")
		
		
}

fun getChannel(id:String,time:Int){
	println("Broadcast for channel $id at $time time")
	
}
}

val tv=TV()
tv.getChannel("5")
tv.getChannel("7",true)
tv.getChannel("3","13:00")


Principles of OOP


Section30:
Interfaces:

video319:
what is an interface
An interface is a definition of a part of a class
Tell you what a class/object can do
Objects can access other objects through their interfaces
very similar to abstract class
can be used as variable types

interface Oven{

val temperate:Int

fun turnOn()
fun turnOff()
fun cook(temp:Int){
	println("Cooking at $temp degrees")
}
}

class Bosch:Oven{

override val temperate=180
override fun turnOn(){
	println("Turning on")
}

override fun turnOff(){
	println("Turning off")
}
}
val myOven:Oven?=null
val boschOven:Oven=getOven()
boschOven.turnOn()
boschOven.cook(150)
boschOven.turnOff()


fun getOven():Oven{
	return Bosch()
}





video321:
Practice Interfaces:

interface Restaurant{

fun provideFood()

fun provideBill()
}


class localRestuarant:Restaurant{
	overrid fun provideFood(){
		println("Your local restuarant provides food and drinks")
	}
	
	override fun provideBill(){
		println("please pay 25")
	}
}

class FancyRestaurant:Restaurant{

overrid fun provideFood(){
		println("This is the most delicious food I have ever tried")
	}
	
	override fun provideBill(){
		println("please pay 100")
	}
}

val rest1:Restaurant=LocalRestaurant()
rest1.provideFood()
rest1.provideBill()

val rest2:Restaurant=FancyRestaurant()
rest2.provideFood()
rest2.provideBill()


video322:
Practice:Interfaces2

interface Car{
	var speed:Int
	fun drive()
	fun park()
}

class BMW:Car{

override var speed:Int=250
override fun drive(){
	println("BMW is driving at $speed kph")
}

override fun park(){
	println("BMW is parking")
}
}


class CarFactory(){

fun provideCar():Car{
	return BMW()
}
}


val factory=CarFactory()
val myCar:Car=factory.provideCar()

myCar.speed=90
myCar.drive()
myCar.park()




Exercise: Interfaces
Coffee will wake you up but also quench your thirst. There are different types of coffee, Arabica and Robusta. But since you don’t really care about that, you just go to the coffee shop and ask for a coffee, which they will happily provide.

You will then drink the coffee to both wake you up and quench your thirst.

Implement this in a program.


video324:


interface Coffee{
fun wakeup()
fun quenchThrist()
}

class Arabica:Coffee{

override fun wakeup(){
println("Waking you up with some Arabica")
}

override fun quenchThirs(){
	println("Quenching your Arabia thrist")
}
}


class Robusta:Coffee{

override fun wakeup(){
println("Waking you up with some Robusta")
}

override fun quenchThirs(){
	println("Robusta will Quench your  thrist for thirst")
}
}


class CoffeeShop{

fun purchaseCoffee():Coffee{
val randomNumber=System.currentTimeMillis()
if(randomNumber%2==0L){
	return Arabica()
}else{
	return Robusta()
}
	
}
}


val myCoffeeShop=CoffeeShop()
var myCoffee:Coffee?=null
for(i in 1..5){

myCoffee=myCoffeeShop.purchaseCofee()
myCoffee.wakeup()
myCoffee.quenchThirst()
}


video325:
More Interfaces:
A class can implement multiple interface

interface PlaceToSit{

}

interface PlaceToSleep{


}

class Couch:PlaceToSit,PlaceToSleep{
}

An interface has no constructor
An interface can implement methods but don't need to
An interface cannot initialize values but can update them

interface PlaceToSit{

var capacity:Int=3 //not allowed
fun increaseCapacity(){
	capacity=4      //OK
}

}


An interface can inherit from another interface

interface Animal{}
interface Mammal:Animal{}
class Puppy:Mammal{}


interface Pet{

var cutenessLevel:Int
fun startPlaying()
fun feed()
}


class Puppy:Pet{

override var cutenessLevel=100
override fun startPlaying(){
	println("Running,jumping, barking")
}

overriding fun feed(){
	println("Give doggy treats")
}
}


class Child{

var myPet:Pet

Init{
	val petStore=PetStore()
	myPet=petStore.getPet()
}


fun raisePet(){
for(i in 1..myPet.cutenessLevel){
myPet?.startPlaying()
}
myPet.feed()
}
}


class petStore{

fun getPet():Pet{
	return Puppy()
}
}



video326: Practice: More Interfaces

interface Food{

fun eat()

}

class FastFood: Food{

override fun eat(){
	println("Fast Food will feed you")
}
}

class FrenchFood:Food{

override fun eat(){
	println("French food will feed you AND delight you")
}
}

class FastFoodRestaurant{
	fun buyFood():Food{
		return FastFood()
	}
}

class FrenchRestaurant{
	fun todaySpecial():Food{
		return FrenchFood()
	}
}

var myFood:Food=FastFoodRestaurant().buyFood()
myFood.eat()

myFood=FrenchRestaurant().todaySpecial()
myFood.eat()

------------

A car will drive you to a destination, but a limousine will drive you there in comfort. A car rental place has both, at different prices.

One day you want a utility car that is cheaper.

Another day, you want a luxury car.

Implement this functionality in a program and display the appropriate messages.


interface RentalCar{

var price:Int
fun rent()
}

class AffordableCar:RentalCar{

override price:Int=1000
override fun rent(){
	println("The affordable car costs 1000")
}
}

class LuxuaryCar:RentalCar{

override var price:Int=5000
override fun rent(){
	println("The luxury car costs 5000")
}
}

class CarDealer{

fun rentAffordableCar():RentalCar{
	return AffordableCar()
}

fun rentLuxuaryCar():RentalCar{
	return LuxuaryCar()
}
}


val dealer=CarDealer()
var myCar=dealer.rentAffordableCar()
myCar.rent()

myCar=dealer.rentLuxuaryCar()
myCar.rent()




Section31:
Standard functions: Functions that can be applied to an object that will take lambda expression and gives you some result in the context of the object.
Standard functions also called Scope functions, Execute code in the context of an object.
Creates a temporary scope while the code is executed

let
with
run 
apply
also
takeIf


In the scope you can access the original object

Person("Alice",20,"Amsterdam").let{printlnln(it)
it.moveTo("London")
it.incrementAge()
println(it)
}

let block will be executed if the object is not null

we can access the object inside let block with it keyword
it refers to the object on which we apply the standard function

There are 5 scope functions, and 2 additional check functions
let
run
with
apply 
also

takeIf 
takeUnless


video332: Let
Allows us to run code on an object
We can access the result as a lambda argument
it by default

val animal=listOf("cat","dog","mouse","bear","zebra")
animals.map{it.length}.filter{it>3}.let{
	println(it)
	println("Size of list is ${it.size}")
}

val animal=listOf("cat","dog","mouse","bear","zebra")
animals.map{it.length}.filter{it>3}.let{ filteredList->
	println(filteredList)
	println("Size of list is ${filteredList.size}")
}


If the block of code contains a single function call, we can use the methodReference ::

val animal=listOf("cat","dog","mouse","bear","zebra")
animals.map{it.length}.filter{it>3}.let( ::println)


A common usecase is to use let to filter for non-null variables

val name=readLine()

name?.let{println("your name is $name")}

video333: Practice: Let

println("Input a number")
val input=readLine()

input?.let{
	val number=it.toInt()
	println("The double of your number is $(number*2)")
	
}



val animals=arrayListOf<String>()
for(i in 1..3){
	println("Input an animal")
	val input=readLine()
	input?.let{
	if(it=="")
		animals.add(null)
	else
		animals.add(it)
	}

}


animals.forEach{
 it?.let{
	println("Feeding the $it")
	}
}

--------------

var isTrue=true
while(isTrue){
var client=readLine()

client?.let{
if(client.toLowerCase() == "stop")
	isTrue=false
else
	println("Hello client $client")

}
}



video 336: With
Perform a block of code on an object
The context is available as 'this'(the this keyword can be omitted)
Can access object variables and methods:
Typical use case:
Perform some initialization on an object
Perform a sequence of actions on an object


with(Car()){
speed=80
drive()
println("Car is driving")

}
 
class Car{
	var speed=50
	fun drive(){
		println("Driving at $speed")
	}
}


using with u can perform sequence of operations on a object that u either create or use the functions of the object passed


class Person{
var firstName="fname"
var lastName="lname"
var age=20

fun printPersonInfo(){
	println("$firstName $lastName is $age years old")
}
}

with(Person()){
	
	firstName="raghu"
	lastName="Sumanth"
	age=28
	printPersonInfo()
}

Exercise: With
A store has a supply of shoes, shirts and jackets, as well as a method to print out the inventory.

Create a variable of type store, update its stock and print out the inventory.

class Store{
var shoes=10
var shirts=20
var jacket=30

fun printInventory(){
	println("The store has $shoes pairs of shoes, $shirts shirts and $jackets jackets.")
}
}

with(Store()){

	shoes=25
	shirts=10
	jackets=43
	printInventory()
}

video340:
Run:
Same as with but invokes as an extension function
Useful when you need a lambda that returns a result

Can be used to limit the scope of variable

val newCar=Car().run{

speed=80
drive()
println("Car is driving")
this

}
println(newCar)

run{

val car=Car()
car.speed=90
car.drive()
println("Car is driving") 
}


class Restaurant{
var standardDish=""
var todaySocial=""

fun printMenu(){
	println("The standard dish is $standardDish")
	println("Today's special is $todaySpecial")
	
}

}

val rest=Restaurant().run{
	standardDish="fish and chips"
	todaySpecial="Fillet mignon"
	printMenu()
	this
}

println(rest)

video343:
class Laptop{
	fun turnoff(){
		println("Turning laptop OFF")
		
	}
	
	fun turnOn(){
		println("Turning laptop ON")
	}
	
	
	
}

fun main(args:Array<String>){
Laptop().run{ turnOff() turnOn()}
}

344: Apply
can be used to apply some functionality and return a result

retuns the initial object
Common use case is applying configuration to an object creation


val myCar=Car().apply{

	speed=80
	color="red"
	startCar()
}

println(myCar::class.java)



class MyCar{

var speed=10
var color="blue"
fun startCar(){
	println("Starting the car,speed is $speed, color is $color")
}
}


Practice Apply:
A lock object needs a key object to unlock
After creating a key, we must define the key secret code and call the 'carve' function


class Lock{

fun unlock(key:Key){

println("Unlocked lock with key $key")
}
}

class Key{

var secretCode=""
fun carve(){
	println("carving the key with code $secretCode")
}
}


Lock().unlock(
Key().apply{
	secretCode="123"
	carve()
}
)





video347:
class CoffeeShop{

fun sellCoffee(name:String){
CoffeeCup().apply{
clientName=name
prepareCoffee()
println("Serving coffee to client $clientName")
println(this)
}

}
}

class CoffeeCup{

var clientName=""
fun prepareCoffee(){
	println("Brewing the coffee")
}
}



val name=readLine()?:""
CoffeeShop().sellCoffee(name)


video348: Also
Used for performing some additional actions on an object

Common use case is adding some actions that don't affect the object such as logging and debugging information

Removing an also block should not affect the execution of a program


Car().apply{

speed=80
run()
println("Car is running")
}
.also{

	println("The car has been started")
	println("Car info: speed= ${it.speed}")
}


Car().apply{

speed=80
run()
println("Car is running")
}
.also{
car->
	println("The car has been started")
	println("Car info: speed= ${car.speed}")
}

class Book{
	fun printBook(){
		println("Printing a book")
	}

}

Book().apply{

printBook()
}.also{
	
	println("Pricing book $it")
	println("Sending an email about book $it")
}



Whenever a car is built, the company logs must be updated and the police notified.

Implement this functionality in a program.




video351:
Whenever a car is built, the company logs must be updated and the policy notified

Implement this functionality in a program


class Car{

fun buildCar(){
	println("Building a car")
}
}

Car().apply{
buildCar()
}.also{
println("LOG: Building the car $it")
println("Sending a message to the police that car $it has been built")
}



video352:
takeIf and takeUnless:
returns the object if the predicate values to true
otherwise returns null

val number=Random.nextInt(100)
val evenOrNull=number.takeIf{it %2==0}

println("the even number is $evenOrNull")
println("The number is $number")


takeUnless: opposite of takeIf
Returns the object if the predicate values to false

for(i in 1..10){

	val number=Random.nextInt(100)
	val oddOrNull=number.takeUnless{it%2==0}

println("the even number is $evenOrNull")
println("The number is $number")
	
}



val numbers=listOf(3,67,34,5,6,3,2,1,4,6,8)
println(numbers)
val newNumbers=arrayListOf<Int>()
for(number in numbers){
	number.takeIf{
		it%2==0
	}?.let{newNumbers.add(it)}
}

println(newNumbers)



val clients=listOf("Alice","Bob","Carol","Alex","Dan")
println(clients)

val newClients=arrayListOf<String>()

for(client in newClients){

	client.takeUnless{it[0]=='A'}?.let{newClients.add(it)}
}

println(newClients)

val arr=arrayListOf<Int>(1,2,3,4,13,5,6,7,8,9,10)
val oddNumbers=arrayListOf<Int>() 
arr.takeIf{
	it%2!=0
}.takeUnless{
	it==13 || it==3
}?.let{
oddNumbers.add(it)
}
println(oddNumbers)


Recap:
let
with
run
apply
also
takeIf
takeUnless

Run code on call chains with let
Perform a block of code with 'with'
Perform a block of code as an extension function with run
Apply functionality and return a result with apply
Add non-essential functionality with also
Filter by predicates with takeIf and takeUnless


Section32:Other types of classes

Data classes
Enum Classes
Sealed classes
Nested classes



Data classes:
Commonly create classes just for storing data
like dto, entity,pojo

Primary constructor has atleast one parameter

All primary constructor parameter need to be val or var
Can have a body but not required


Data classes:
data class User(val name:String, val email:String, val password:String)


val user=User("john","john@gmail.com","johnpwd")

println(user)


DataClass methods:
Automatically generated class methods
.equals() or ==
compares data not object references

.toString()
Prints out variable names and data

.copy()
Creates a copy with only some data changed


ex:
data class User(val name:String, val email:String, val password:String)
val user=User("john","john@gmail.com","johnpwd")
val user1=User("john","john@gmail.com","johnpwd")


println(user==user1) //true


class RegularUser(val name:String, val email:String, val password:String)
val user=RegularUser("john","john@gmail.com","johnpwd")
val user1=RegularUser("john","john@gmail.com","johnpwd")


println(user==user1) //false
***
Regular class will compare object references but data class compares content

data classes compare data and not object references



.toString()

Regular class print the objecttype@objectrefeences

with data class it prints the data of the object

println(user)
println(user.toString())


.copy()

val myuser3=user.copy(email="test@gmail.com")
//changes email and rest of fields are copied as is

println(myUser3)

video360:

data class Customer(val name:String,val email:String,val productsBrought:Int)

val customers=arrayListOf<Customer>()

customers.add(Customer("Alice","alice@gmail.com",7))
customers.add(Customer("Bob","bob@gmail.com",3))
customers.add(Customer("Carol","carol@gmail.com",6))

println(customers)

val newCustomer=customers[1].copy(email="bobnewemail@gmail.com")
customers.add(newCustomer)
println(customers)


fun sendEmail(customers:ArrayList<Customer>){

customers.forEach{println("Sending an email to ${it.email}"}
}




video361:
A network server responds with this information about blog articles

Title

Content

Number of readers

You receive 2 articles from the server.

Update the title to suit your blog but also keep the originals.

Print out all the article information.

data class Article( val title:String, val content:String,val numberOfReaders:Int);

fun getArticle():Article{

val randomTitle="Title "+Random.nextInt(100)
val numberOfReaders= Random.nextInt(1000)
return Article(randomTitle,"Some content",numberOfReaders)


}

val articles=arrayListOf<Article>()
for(i in 1..10)
	articles.add(getArticle())

val newArticles=arrayListOf<Article>()

for(article in articles){
newArticles.add(article)
val newArticle=article.copy(title=article.title+" for my blog")
newArticles.add(newArticle)

}
//java.util.ConcurrentModificationException

newArticles.forEach{println(it)}



video363:
Enum Classes
Define a collection of constants
The constants defined are objects

enum class Color{

RED,
GREEN,
BLUE

}

CONSTANTS are object, we can defined of the type

fun decide(color:Color){
when(color){
	Color.RED ->{println("you chose red")}
	Color.GREEN ->{println("you chose green")}
	Color.BLUE ->{println("you chose blue")}
}
}


val color=Color.RED
Enum constants can be initialized
Constants have properties like name, oridinal








enum class Color{

RED(23),
GREEN(32),
BLUE(12)

}

colors.GREEN.timeUser
clor.RED.name
Color.BLUE.ordinal


enum Class GameState{

STARTED,
PLAYING
GAMEOVER
}

fun changeState(currentState:GameState):GameState{

return when(currentState){

GameState.STARTED-> Gamestate.PLAYING
GameState.PLAYING-> Gamestate.GAMEOVER
GameState.GAMEOVER-> Gamestate.STARTED
}
}

var currentState=GameState.STARTED
for(i in 1..10){
println("${currentState.ordinal+1} $currentState")
currentState=changeState(currentState)
}



Exercise: Enum classes
The medals in the olympics are

GOLD - 1st place

SILVER - 2nd place

BRONZE - 3rd place

NONE - other

Create a class Olympics that has a function which returns the medal a contestant won based on the position they finished on.
It also has a function which returns the position of a contestant based on the medal they won.
Create an object of that class and call its methods.

enum class Medal(val position:Int){
GOLD(1),
SILVER(2),
BRONZE(3),
NONE(4)
}

class Olympics{

fun getMedal(position:Int):Medal{

return when(position){
	1->Medal.GOLD
	2->Medal.SILVER
	3->Medal.BRONZE
	else->Medal.NONE
}
}
}

fun getPosition(medal:Medal)=medal.position

val olympics=Olympics()
println(olympics.getMedal(2))
println(olympics.getMedal(7))

println(olympics.getPosition(Medal.GOLD))
println(olympics.getPosition(Medal.BRONZE))

video367:
Sealed Classes: related to Enum classes defines constants but they are basically a class

Define a restricted hierarchy
Abstract by default so cannot be instantiated
useful in when expressions


abstract class Plant
sealed class Fruit:Plant()
class Apple:Fruit()
sealed class Vegetable:Plant()
class Potato:Vegetable()
fun getPlat():Plant=Apple()

val somePlant=getPlant()

when(somePlant){

is Fruit-> println("Sweet")
is Vegetable->println("Tasty")

}



A function getVehicle retuns a type Vehicle that can either be a car or a bicycle
If a bicycle is returned, print out a message saying it's more healthy
If a car is returned, print out a message saying it's faster


abstract class Vehicle
sealed class Car:Vehicle()
sealed class Bicycle:Vehicle()

class BMW:Car()
class Pegasus:Bicycle()

fun getVehicle():Vehicle=Pegasys()

val myVehicle=getVehicle()
when(myVehicle){
	is Car-> println("A car is faster")
	is Bicycle-> println("A Bicycle is more healthy")
}



Exercise: Sealed classes
A lottery returns prizes. It can either return a car, a vacation or a gift card.
A function lottery returns prizes every time it is called. It will randomly return one of the three types of prizes.
Print out a specific message for each type of prize won.


abstract class Prize
sealed class Car:Prize()
sealed class Vacation:Prize()
sealed class Giftcard:Prize()
class VW:Car()
class FranceHoliday():Vacation()
class Dollar10:GiftCard()

fun lotter():Prize{
val value=Random.Int(3)
return when(value){
	0-> return VW()
	1->return FranceHoliday()
	else ->Dollar10()
}
}

val prize:Prize=lotter()

when(prize){
	is Car-> println("you won a car")
	is Vacation-> println("you won a vacation")
	is Giftcard-> println("you won a gift card"0
}



video371:
Nested classes
A nested class is created inside another class

class Car{

private val engine=Engine()
var speed=100
fun drive(){
	engine.run()
	println("Driving at $speed")
}

private inner class Engine{
 val rpm=300
 fun run(){
	println("Engine running")
	this@Car.speed=150
	this$Car.drive()
 }
}
}


val myCar=Car()
//myCar.Engine().run()
myCar.drive(0

this@Car is the reference



class Computer{

fun bootUp(){
	println("Booting up computer")
	val os=OperatingSystem()
	os.startOS()
	println("Computer ready")
}

inner class OperatingSystem{

fun startOS(){
	println("OS started")
}
}
}


Exercise: Nested classes
In order for an airplane to take off, it needs to have 2 engines, and they both need be running.
Create an Airplane class that has a takeoff method, which starts the engines and prints a take off message.


class Airplane{

private val engine1=Engine("engine1")
private val engine2=Engine("engine2")

fun takeoff(){
engine1.startEngine()
engine2.startEngine()
println("take off completed")
}

private inner class Engines(val name: String){
	fun startEngines(){
		println("Engines $namestarted")
	}
}
}


val myPlane=Airplane()
myplane.takeOff()


Other types of classes:
what data classes are and how they store data
what enum classes are and how they define constans
what sealed classes are and how they define types
what nested classes are and how they encapsulate functionality

Section33: Extensions:
Extensions
Extension functions
Extension properties
Companion object extensions

Extensions:
Allow us to extend a class that we don't own or cannot modify

without the need to inherit from that class
Add functionality that is available in the context of our program only
Added code can be called in the usual way
by declaring objects of that class and invoking methods


Can extend:
Functions
Properties
Companion Object


Extension functions:
Can add functions to class that we don't own or cannot modify

Can access the object using the 'this' reference

fun String.slim()=this.substring(1,length-1)

val name="michale"
println(name.slim())

The original class is not actually modified
The new functions are not actually inserted in the class
Rather, it's a shortcut to make the functions available using the usual object.function notation


extension Properties:
Can add properties to class, in a similar way to functions

val String.betterLength:Int
			get(){
		println("Getting the better length")
			return 200
		}

val name="Michael"		
println(name.betterLength)


They cannot be local: declared inside a function or class

Cannot update an extension property
can only use values(val), not variables(var)

The property is not actually inserted into the class
The extension properties are a shortcut for the . notation

therefore initializers are not allowed

val String.betterLength=7 //error


fun String.getCustomName()="A string of characters"
fun Int.getCustomName()="A Integer number"
fun Float.getCustomName()="A floating point number"


println("SomeString".getCustomName())
println(3.getCustomName())
println(2.5F.getCustomName())



Exercise: Extension functions
Add an extension function to the ArrayList class that returns a message saying how many elements the list contains.

Create an ArrayList and print out the extension function message.

fun ArrayList<Int>.message() ="no of elements: ${size}"

val newList=arrayListOf(3,4,6,4,3,2)
newList.message


Companion Object extensions:
If a class has a companion object defined, we an extend it with functions and properties

if not, we cannot add a companion object

class Book{
	companion object{}
}

fun Book.Companion.printMe(){
	println("Car companion object")
}

Book.printMe()
//Companion objects allow us to add static functionality to the class
that is we don't need to create an object to access  the companion object functionality
we can simply access it through class itself



fun String.Companion.message(){
	println("This is a String class")
}

String.message()

Add a companion object function to the Double class that prints out the class name.

Call the companion object extension function.



fun Double.Companion.getName(){
	println("Double type")
}

Double.getName()


Section Generics:
Section Objectives:

Generics
Type Constraints
Generic Type Parameters

video389:
Generic type is the type we provide
A class can have type parameters
The type can be used by variables and methods
Useful when a class can handle multiple types of parameters

val animals:ArrayList<String>=arrayListOf("cat","dog","mouse")


Generic Type parameters
If a class has a functionality we can assign a generic to it so that we can rely up on doing some functionality of the code
for arrayList we need to provide type so that it can perform certain operations


you can create your own classes and allow to take these types of parameters

Class Box<T>{

fun display(item:T){
	println(item)
}
}


val myBox=Box<String>()
myBox.display("Contents")



class Car{

}

val carBox=Box<Car>()
carBox.display(Car())


We can have multiple generics, separated by commas
val dictionary=hashMapOf<String,String>()



Class NewBox<T,U>{

fun display(item:T,itemU:U){
	println(item)
	println(itemU)
}
}


val newBox=NewBox<String,String>()
newBox.display("testing","testingagain")

video390: Practie Generics

class GType<T>{

fun gFun(item:T){
	println(item.toString().length)
}
}

val info=GType<String>()
info.gFun("some String")

val info2=GType<Double>()
info2.gFun(34.55545)

val info3=GType<ArrayList<String>>()
info3.gFun(arrayListOf(3,4,5,6,4,2,2,3,5))



class GTType<T>{

fun exFun(item:T){
	println(item.toString())
}
}

val type1=GTType<Float>()
type1.exFun(3445.33F)

val type2=GTType<HashMap>()
type2.exFun(hashMapOf(Pair("one",1),Pair("two",21),Pair("three",11))


Type Constraints:

we can restrict the type of generic parameters

abstract class Fruit{

	abstract fun peel()
}

class Apple:Fruit(){
	override fun peel(){
		println("Peeling the apple")
	}
}


class Banana:Fruit(){
	override fun peel(){
		println("Peeling the banana")
	}
}


class Chef<T:Fruit>{

	fun cook(item:T){
		item.peel()
	}
}

val chef=Chef<Apple>()
chef.cook(Apple())


val chef=Chef<Banana>()
chef.cook(Banana())


for multiple constraints, we can separate them by comma

class Box<T:Fruit,U:Vegetable>{
fun display(item:T){
	println(item)
}

}

video394: Type Constraints

A class can take a generic type of collection of strings. It has a function iterates through the elements, converts them to string and prints them out to the console

Instantiate the class with different types of collections and call the function.

class Printer<T:Collection<String>>{

fun iterate(collection:T){
	collection.forEach{println(it)}
}
}


val printer1=Printer<Set<String>>()
printer1.iterate(hashSetOf("alice","bob","carol"))

val printer2=Printer<List<String>>()
printer2.iterate(listOf("Dan","Ellen","fran","George"))



Exercise: Type constraints
Create an abstract class Shape that defines a method getArea which takes an argument size. Create two subclasses, Square and Circle, that inherit from Shape, and implement the method.

Square area = size * size

Circle area = size * size * 3.1415

Create another class Geometry that takes a generic argument of type Shape, and has a method that prints a message which includes the area of the shape that is passed.

Instantiate the Geometry class and print the area of the shape.


abstract class Shape{
abstract fun area(size:Int):Double

}

class Square:Shape(){
	override fun area(size:Int)=size*size.toDouble()
}


class Circle:Shape(){

	override fun area(size:Int)=size*size*3.1415
}

class Geometry<T:Shape>{

fun getMessage(shape:T,size:Int){
	println("The area of this shape is ${shape.area(size)}")
}
}


val geo1=Geometry<Square>()
geo1.getMessage(Square(),5)
val geo2=Geometry<Circle>()
geo2.getMessage(Circle(),8)


Section Recap:
How to pass type parameters to classes
How to restrict the type parameter types


section35: Other concepts
Type casting - is, as
lateinit
lazy


is used to check whether an object is a certain type and allows us to convert an object into certain types

val value="Testing my Strings"

if( value is String){
	println("${value.length} characters")
}

!is
open class Car{}

class BMW:Car(){}
val myCar:Car=getCar()

if(myCar !is BMW){
	println("This is not my favorite brand") 
}

val myCar:Car=getCar()
if(myCar !is BMW){
	println("This is not my favorite brand")
}


as: converts an object into a different type


open class Car{}
class BMW:Car{

fun drive(){
	println("Driving my BMW")
}

}


val myCar:Car=getCar()

if(myCar is BMW)
	(myCar as BMW).drive()
	

	
	Null safe operator as?
	
open class Car{}
class BMW:Car{
	fun drive(){
		println("Driving my BMW")
	}
}

val myCar:Car=getCar()

val bmwCar=myCar as? BMW
bmwCar?.drive()


TypeCasting:
An FTPService class inherits from the NetworkService class and ads a method transferFile()

A function returns a Network Service

In the main program invoke the function and if the service is of type FTPService, call the transferFile() function


open class NetworkService{}

class FTPService:NetworkService(){
	fun transferFile(){
		println("Transferring a file via FTP")
	}
}


fun getNetworkService():NetworkService{

return if(Random.nextInt()%2==0)
	NetworkService()
	else
	FTPService()
}

for(i in 1..10){
	val service=getNetworkService()
	(service as? FTPService)?.transferFile()
}

Exercise: type casting
The classes Cat and Dog inherit from an abstract class Animal. The Cat class has a function purr() and the Dog class has a function bark()

A function provides a list of animals, that are randomly distributed.

Design a program that invokes each respective function of each type of Animal from the list.

video402:
abstract class Animal

class Cat:Animal(){
fun purr(){
	println("Dog is purring")
	
}


}

class Dog:Animal(){

fun bark(){
	println("Dog is barking")
	
}
}


fun getAnimal():ArrayList<Animal>{

val animals=arrayListOf<Animal>()
for(i in 1..20){
	animals.add(
	if(Random.nextInt()%2==0)
		Dog()
	else
		Cat()
	)
}

return animals
}

val animals=getAnimals()
animals.forEach{
	animal->(animal as? Dog)?.bark()
			(animal as? Cat)?.purr()
}




video403:
lateinit
Allows us to create non null, non initialized variables

Need to initialize the variable before using it
Accessing it before initializing it throws an exception

Can be used only on var variables

use .isInitialized to check initialization

lateinit var networkService:String
networkService=getNetworkService()
println(networkService)


lateinit var networkService:String
println(networkService) //Exception

fun getNetworkService()="NetworkService"


Common use cases:
Dependency Injection
unit testing

video404: Practice lateinit

class Country{

private lateinit var name:String
fun setName(name:String){
	this.name=name
}

fun getName()=name
}


val myCountry=Country().apply{setName("Sweden")}

println("Hellow ${myCountry.getName()}!")


video405: Exercise lateinit
Exercise: lateinit
Define a variable message as a String. Then define a list of prime numbers.

A function takes the list of integers and randomly returns one of them. Use it to initialize the message variable with a message including the returned prime number.

Print out the message. *



* This exercise can easily be solved in a way that doesn’t use lateinit var. For the sake of practice, please use it in this case.



video406:
Solution
lateinit var message:String
val primeNumbers=listOf(2,3,5,11,7,13,17,23,37)

message="The chosen prime number is ${selectPrimeNumber(primeNumbers)}"
println(message)


fun selectPrimeNumber(primes:List<Int>)=primes.random()



video407: lazy
for memory and performance optimization

Lazy variables are variables that are initialized when needed


Useful to save memory in case the variable is never accessed

val someLargeVariable:String by lazy{"A large value"}

val rand=Random.nextInt()

if(rand%2==0)
	println(someLargeVariable)
	

video408: Practice lazy

fun generateList():List<Int>{
	val integers=arrayListOf<Int>()
	
	for(i in 1..1000){
		integer.add(Random.nextInt(10000))
	}
	return integers
}

val list:ArrayList<Int> by lazy {generateList()}

println("Should the list be generated? (yes/no)")
val input=readLine()?:""
if(input=="yes")
	println(list)

	
	
Exercise: lazy
An object of a class NewUser is created for each new user. It contains a function to print a welcome message.

In your program, you have a list of banned usernames.

Ask the user to input their desired username. If it is not part of the list, create the NewUser object and print the welcome message.


class NewUser{

	fun printWelcome(){
		println("Welcome to the course!")
	}
}

val newUser:NewUser by lazy{NewUser()}

val banned:List<String>=listOf("Alice","Bob","Carol","")

val input:String=readLine()?:""
if(!banned.contains(input))
	newUser.printWelcome()
	
	
Other concepts:
Type casting - is, as
lateinit
lazy


Section36:
Building a GUI application in Kotlin

Calculator Project description

objectives:
Build a visual calculator
Design a GUI app(non-android)
Learn about gradle

Technologies used:
Kotlin
Gradle
TornadoFX
fxml and css



Section37:
First Android application

video420
Build a Hello World App
Intall Android Studio(short version)
Install Android Studio(long version)
Create a new app
Build the functionality and run it


video421:
Installing Android studio(Short version)
developer.android.com/studio



Section38:
Coroutines and asynchronous Programming
Video427: Solution Objectives

Multithreading
Coroutines
Coroutine Concepts
Scope, suspending functions, context etc



video428: Multi-threading
A thread is a sequence of execution running in parallel
Sequential programming- all instructions are executed in order
Prallel Programming- sets of instructions are executed in parallel

tasks should be running in parallel, if they have any dependency they should be having 
some synchorization to interact with each other

Won't block UI thread- will make programs responsive

Benefits:
responsiveness
faster execution
Parallelisation(better CPU Utilisation)
respource efficiency

Drawbacks:
Synchronisation
Error handling

Coroutines:
why Coroutines:
Threads are resource Intensive

Coroutines are light weight threads
coroutines uses thread pools
Simplify async code, callback and synchronisation
Simple syntax
can pause and resume at any time, on any no of threads
a thread is a place to execute coroutine, a coroutine itself can be stopped and restarted at any time.
in that way coroutines are light weight and can be reused as many no of times u like

basic concepts of coroutines:
Scope: create and run coroutines, provides lifecycle events
like pausing, stopping, cancelling is handled by scope

Context: the scope provides a context in which the coroutine runs
scope itself provides a context, context is simply the state of a coroutine.
provides some variables and functionality that u can reuse in coroutine,

Suspending functions- functions that can run in a coroutine(can be suspended)


Jobs is a handle on coroutine, u can use a job to access lifecycle methods of a coroutine.
Deferred- it is basically a coroutine which returns the result but sends coroutine in parallel,
but result will not be sent immeidately, it will be sent only when coroutine is completed  execution
Deferred is a future result of coroutine, tells the program to wait for the output of coroutine when u are at a point u need the result

Dispatcher- manages which threads the coroutine runs on
threre are some dispatchers listed belwo

Error handling- 


video430:
Hello World


Scope:
Provides lifecycle methods for coroutines
allows us to start and stop coroutines


GlobalSope.launch{} the scope of the coroutine is the lifecycle of the entire application
this coroutines will not get finished, if it is running in the background it won't be stopped unless entire application is stopped
GobalScope is a large scope we generally will not use it.
it is simple and easy to create a background coroutine in a simple way but not generally used

runBlocking: creates a scope and runs a coroutine in a blocking way.
This also not used very often, we use it when we want to stop the execution of any code and run coroutine
another situation is this is the only thing our program does that is while showing coroutine examples

coroutineScope{} :
creates a new scope, doesnot complete until all children coroutines complete
we are creating a scope and creating multiple coroutines in it
the coroutine we start here will not complete until all inner coroutines completes


usage of above scopes
runBlocking{
launch{
	delay(1000L)
	println("Blocking task")
}
} 


GlobalScope.launch{

	delay(1000L)
	println("Global scope")
}

coroutineScope{
	delay(1000L)
	println("custom coroutine scope")    
}


video432: Context
concept of coroutine context is tightly related to the scope
A context is a set of data that relates to the coroutine
All coroutines have an associated context

scope is used to create and manage coroutine,that means u can create/stop them when inner coroutines have finished
All coroutines have an associated context
context is set of variables  and data associated with coroutine
Important elements of a context:
Dispatcher: which thread the coroutine is run on
Job: handle on the coroutine lifecycle

runBlocking{

	launch(CoroutineName("myCoroutine")){
		println("This is run from ${this.coroutineContext.get(CoroutineName.Key)}")
	}
}


Suspending Functions:
it is simply a function that can run in a coroutine
If u try to access a function from coroutine u will get an error, unless u make it a suspending function

they makes callbacks seamless
u can execute a code in coroutine and when u need to access local variable in your main program,
u can do it easily within a function, we will see that in the code

suspend fun sayHello(){
	println("Hello!")
}
 
 
video 434: Jobs
it is basically a handle on the coroutine
a piece of code that is running in the background
A .launch() call returns a job
Allows us to manipulate the coroutine life cycle

Live in the hierarchy of other jobs
both as parents or children

Job{

Job{}
Job{
	Job{}
}
}


val job1=GlobalScope.launch{

	coroutineScope{
		val job2=launch{}
	}
}


can access lifecycle variables and methods
cancel()
join()

If a job is cancelled, all its parents and children will be cancelled too



video435:
Dispatchers
A dispatcher determines which thread or thread pool the coroutine runs on
not mandatory to define a dispatcher if u don't want to.

we can define coroutines as we did so far without specifying which dispathcer we need
If u want to explicitly specify which dispatcher to use, we can specify

Different dispatchers are available depending on the task specificity

some dispatchers are more suitable for network communications other are for processing a large amount of data
others are for UI and communications etc

launch(Dispatchers.Default){

//do some CPU intensive processing task here

}



Common dispatchers:
Main: Main thread update in UI driven applications(ex: Android)
Main dispatcher needs to be defined in Gradle

UI cannot be updated unless u are on Main thread

Default: Useful for CPU intensive work, like data processing, image processing should usually done with Default dispatcher

IO: useful for network communication or reading/writing files

Unconfined: Starts the coroutine in the inherited dispatcher that called it
here we will not define the dispatcher, the system will decide the dispatcher which is the parent

newSingleThreadContext("MyThread")
Forces creation of a new thread
NOT used as threads are expensive, better to use coroutines

Unconfined dispatcher has another particularity is that when coroutine is paused when it is resumed it will switch threads

Pausing a Unconfined Coroutine and restarting it will change the thread it is running


video436:
async

Just like launch, expect it returns a result
In the form of a Deferred
Deferred is like a promise, that at some point we will be able to get a result, it just not available right now
a future promise of a returned value
When we need the value, we call await()(blocking call)
If the value is available, it will return immediately
If the value is not available, it will pause the thread until it is

suspend fun getRandom()=Random.next(1000)

val valueDeferred=GlobalScope.async{getRandom()}
//Do some processing here

val finalValue=valueDeferred.await()

 video437: withContext
 A function commonly used in coroutines is withContext
 Allows us to easily change context
 Easily switch between dispatchers
 very lightweight
 
 launch(Dispatchers: Default){
 
 //default context
 withContext(Dispatchers.IO){
	//IO Context
 }
 
 //back to default context
 
 }
 
  
 video 438:
 Exception handling
 Exception behaviour depends on the coroutine builder
 
 launch:
 propagates through the parent child hierarchy
 The exception will be thrown immediately and jobs will fail
 Use try-catch or an exception handler
 
 
 async:
 Exceptions are deferred until the result is consumed
 If the result is not consumed, the exception is never thrown
 try-catch in the coroutine or in the await() call
 
 
 val myHandler=CoroutineExceptionHandler(coroutineContext,throwable->
 //handle exception
 
 }
 
 launch(myHandler){
	//do some task here
	throw IndexOutOfBoundException()
 }
 
 launch(Dispatchers.Default + myHandler){
	//do some task here
	throw IndexOutOfBoundException()
 }
 
 
 section 39: Android Coroutines: Image processing
section objectives

Objective:
Get an image form a URL
Apply processing
Show it in an image view

Requirements:
Android studio installed
Android knowledge


https://github.com/CatalinStefan/AndroidCoroutinesImageProcessing

video440: Setting up the project

Add these dependencies to your module level (app) build.gradle file

implementation 'org.jetbrains.kotlinx:kotlinx-coroutines-core:1.3.0'
implementation 'org.jetbrains.kotlinx:kotlinx-coroutines-android:1.3.0'

 
 
 https://eventsonair.withgoogle.com/events/kotlin/watch?talk=kotlin101
 What is Kotlin
 Kotlin evolution
 Why kotlin
 Kotlin adoption
 Coding in kotlin
 Build fro Multiplatform
 Coroutines
 Appendix
 
 
 what is kotlin:
 Modern Programming language inspired from java, python, C#
 OOP+FP
 Statically typed : type of data is determined at compile time, helps to catch many error at compile time. has power type interference, no need to define the type explicitly
 Open Source(Apache 2.0)
in 202 Kotline 1.4 preview is released

	why kotlin?
	Concise/Expressive
	Code safety
	Interoperability
	Tool friendly
	Structured concurrency: for background operations like network calls/DB operations our code can become compitative, there will be bunch of callbacks and hard to debug..for this we have coroutines which makes code more sequential so it is easier to read
	#4th most loved language on stack overflow
	

basic syntax:	
 Mutable variables:
 var num:Int=1
 
 Immutable variables:
 val greeting="Hello"
 
 basic types:
 Int
 Double
 Boolean
 Char
 String
 
 Mathematical Operators : + - * / %
 Increment and decrement Operators: ++ --
 Comparision Operators:  > < >= <=
 Assignment Operator: =
 Equality Operators: == !=
 
 Simple Program:
 fun main(){ //string args is optional in kotlin
	println("Hello World")
 }
 
 
 Functions:
 fun main(){
	val number1:Int=10
	val number2=20
	val total=addNumbers(number1,number2)
	println("Sum of two numbers: $total")
	
 }
 
 fun addNumbers(num1:Int,num2:Int):Int{
	return num1+num2
 }
 
 
 Compact functions:
 fun double(x:Int):Int{
	x*2
 }
 
 fun double(x:Int)=x*2
 
 
 Lambdas:
 var dirtyLevel=20
 val waterFilter={dirty:Int ->dirty/2}
 println(waterFilter(dirtyLevel))
 
 
 Higher Order functions:
 
 fun encodeMsg(msg:String,encode:(String)->String):String{
	return encode(msg)
 }
 
 val enc1:(String)->String={input->input.toUpperCase()}
 println(encodeMsg("abc",enc1))
 
 Concise/Readability:
 https://eventsonair.withgoogle.com/events/kotlin/watch?talk=kotlin101'
 24:00
 
 
 
 