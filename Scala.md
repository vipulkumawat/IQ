**Scala Programming:**
Scala combines object-oriented and functional programming in one concise, high-level language. Scala's static types help avoid bugs in complex applications, and its JVM and JavaScript runtimes let you build high-performance systems with easy access to huge ecosystems of libraries.
Intro: https://docs.scala-lang.org/tour/tour-of-scala.html


```
Scala is a modern multi-paradigm programming language designed to express common programming patterns in a concise, elegant, and type-safe way.
smoothly integrates the features of object-oriented and functional languages. 
Scala  is a hybrid functional programming language.
Scala is compiled to run on the Java Virtual Machine. 
Scala is pure object-oriented language in the sense that every value is an object. 
Types and behavior of objects are described by classes and traits which will be explained in subsequent chapters.
Classes are extended by subclassing and a flexible mixin-based composition mechanism as a clean replacement for multiple inheritance.

Scala is functional:
Scala is also a functional language in the sense that every function is a value and every value is an object so ultimately every function is an object.
Scala provides a lightweight syntax for defining anonymous functions, it supports higher-order functions, it allows functions to be nested, and supports currying. These concepts will be explained in subsequent chapters.
Scala is statically typed
Scala, unlike some of the other statically typed languages (C, Pascal, Rust, etc.), does not expect you to provide redundant type information. You don't have to specify a type in most cases, and you certainly don't have to repeat it.
Scala runs on the JVM
Scala is compiled into Java Byte Code which is executed by the Java Virtual Machine (JVM). This means that Scala and Java have a common runtime platform. You can easily move from Java to Scala.

The Scala compiler compiles your Scala code into Java Byte Code, which can then be executed by the 'scala' command. The 'scala' command is similar to the java command, in that it executes your compiled Scala code.

Scala can Execute Java Code:
Scala enables you to use all the classes of the Java SDK and also your own custom Java classes, or your favorite Java open source projects.

Scala can do Concurrent & Synchronize processing:
Scala allows you to express general programming patterns in an effective way. It reduces the number of lines and helps the programmer to code in a type-safe way. It allows you to write codes in an immutable manner, which makes it easy to apply concurrency and parallelism (Synchronize).


Scala vs Java
Scala has a set of features that completely differ from Java. Some of these are −

All types are objects
Type inference
Nested Functions
Functions are objects
Domain specific language (DSL) support
Traits
Closures
Concurrency support inspired by Erlang


Scala Web Frameworks
Scala is being used everywhere and importantly in enterprise web applications. You can check a few of the most popular Scala web frameworks −
The Lift Framework
The Play framework
The Bowler framework


Environment requirement:
JDK1.8+
set JAVA_HOME
Add JAVA_HOME/bin to Path
verify scala version: scala -version

 the ';' line end character is optional in scala
Object − Objects have states and behaviors. An object is an instance of a class. Example − A dog has states - color, name, breed as well as behaviors - wagging, barking, and eating.

Class − A class can be defined as a template/blueprint that describes the behaviors/states that are related to the class.

Methods − A method is basically a behavior. A class can contain many methods. It is in methods where the logics are written, data is manipulated and all the actions are executed.

Fields − Each object has its unique set of instance variables, which are called fields. An object's state is created by the values assigned to these fields.

Closure − A closure is a function, whose return value depends on the value of one or more variables declared outside this function.

Traits − A trait encapsulates method and field definitions, which can then be reused by mixing them into classes. Traits are used to define object types by specifying the signature of the supported methods.


example program:
object HelloWorld {
   /* This is my first java program.  
   * This will print 'Hello World' as the output
   */
   def main(args: Array[String]) {
      println("Hello, world!") // prints Hello World
   }
}

Open the command prompt window and go to the directory where the program file is saved. The ‘scalac’ command is used to compile the Scala program and it will generate a few class files in the current directory. One of them will be called HelloWorld.class. This is a bytecode which will run on Java Virtual Machine (JVM) using ‘scala’ command.

\> scalac HelloWorld.scala
\> scala HelloWorld


Basic Syntax
The following are the basic syntaxes and coding conventions in Scala programming.

Case Sensitivity − Scala is case-sensitive, which means identifier Hello and hello would have different meaning in Scala.

Class Names − For all class names, the first letter should be in Upper Case. If several words are used to form a name of the class, each inner word's first letter should be in Upper Case.

Example − class MyFirstScalaClass.

Method Names − All method names should start with a Lower Case letter. If multiple words are used to form the name of the method, then each inner word's first letter should be in Upper Case.

Example − def myMethodName()

Program File Name − Name of the program file should exactly match the object name. When saving the file you should save it using the object name (Remember Scala is case-sensitive) and append ‘.scala’ to the end of the name. (If the file name and the object name do not match your program will not compile).

Example − Assume 'HelloWorld' is the object name. Then the file should be saved as 'HelloWorld.scala'.

def main(args: Array[String]) − Scala program processing starts from the main() method which is a mandatory part of every Scala Program.



Scala Identifiers
All Scala components require names. Names used for objects, classes, variables and methods are called identifiers. A keyword cannot be used as an identifier and identifiers are case-sensitive. Scala supports four types of identifiers.

Alphanumeric Identifiers
An alphanumeric identifier starts with a letter or an underscore, which can be followed by further letters, digits, or underscores. The '$' character is a reserved keyword in Scala and should not be used in identifiers.

Following are legal alphanumeric identifiers −

age, salary, _value, __1_value
Following are illegal identifiers −

$salary, 123abc, -salary

Operator Identifiers
An operator identifier consists of one or more operator characters. Operator characters are printable ASCII characters such as +, :, ?, ~ or #.

Following are legal operator identifiers −

+ ++ ::: <?> :>
The Scala compiler will internally "mangle" operator identifiers to turn them into legal Java identifiers with embedded $ characters. For instance, the identifier :-> would be represented internally as $colon$minus$greater.

Mixed Identifiers
A mixed identifier consists of an alphanumeric identifier, which is followed by an underscore and an operator identifier.

Following are legal mixed identifiers −

unary_+, myvar_=
Here, unary_+ used as a method name defines a unary + operator and myvar_= used as method name defines an assignment operator (operator overloading).

Literal Identifiers
A literal identifier is an arbitrary string enclosed in back ticks (` . . . `).

Following are legal literal identifiers −

`x` `<clinit>` `yield`
Scala Keywords
The following list shows the reserved words in Scala. These reserved words may not be used as constant or variable or any other identifier names.

abstract	case	catch	class
def	do	else	extends
false	final	finally	for
forSome	if	implicit	import
lazy	match	new	Null
object	override	package	private
protected	return	sealed	super
this	throw	trait	Try
true	type	val	Var
while	with	yield	 
-	:	=	=>
<-	<:	<%	>:
#	@		
Comments in Scala
Scala supports single-line and multi-line comments very similar to Java. Multi-line comments may be nested, but are required to be properly nested. All characters available inside any comment are ignored by Scala compiler.


Multiline:
/* This is my first java program.  
    * This will print 'Hello World' as the output
    * This is an example of multi-line comments.
    */

singleline:
  // Prints Hello World

Blank Lines and Whitespace
A line containing only whitespace, possibly with a comment, is known as a blank line, and Scala totally ignores it. Tokens may be separated by whitespace characters and/or comments.

Newline Characters:
Scala is a line-oriented language where statements may be terminated by semicolons (;) or newlines. A semicolon at the end of a statement is usually optional. You can type one if you want but you don't have to if the statement appears by itself on a single line. On the other hand, a semicolon is required if you write multiple statements on a single line.
val s = "hello"; println(s)

Scala Packages
A package is a named module of code. For example, the Lift utility package is net.liftweb.util. The package declaration is the first non-comment line in the source file as follows −

package com.liftcode.stuff
Scala packages can be imported so that they can be referenced in the current compilation scope. The following statement imports the contents of the scala.xml package −

import scala.xml._
You can import a single class and object, for example, HashMap from the scala.collection.mutable package −

import scala.collection.mutable.HashMap
You can import more than one class or object from a single package, for example, TreeMap and TreeSet from the scala.collection.immutable package −

import scala.collection.immutable.{TreeMap, TreeSet}


Apply Dynamic
A marker trait that enables dynamic invocations. Instances x of this trait allow method invocations x.meth(args) for arbitrary method names meth and argument lists args as well as field accesses x.field for arbitrary field namesfield. This feature is introduced in Scala-2.10.

If a call is not natively supported by x (i.e. if type checking fails), it is rewritten according to the following rules −

foo.method("blah") ~~> foo.applyDynamic("method")("blah")
foo.method(x = "blah") ~~> foo.applyDynamicNamed("method")(("x", "blah"))
foo.method(x = 1, 2) ~~> foo.applyDynamicNamed("method")(("x", 1), ("", 2))
foo.field ~~> foo.selectDynamic("field")
foo.varia = 10 ~~> foo.updateDynamic("varia")(10)
foo.arr(10) = 13 ~~> foo.selectDynamic("arr").update(10, 13)
foo.arr(10) ~~> foo.applyDynamic("arr")(10)


Scala DataTypes:
Scala has all the same data types as Java, with the same memory footprint and precision. 

Byte
8 bit signed value. Range from -128 to 127

Short
16 bit signed value. Range -32768 to 32767

Int
32 bit signed value. Range -2147483648 to 2147483647

Long
64 bit signed value. -9223372036854775808 to 9223372036854775807

Float
32 bit IEEE 754 single-precision float

Double
64 bit IEEE 754 double-precision float

Char
16 bit unsigned Unicode character. Range from U+0000 to U+FFFF

String
A sequence of Chars

Boolean
Either the literal true or the literal false

Unit
Corresponds to no value

Null
null or empty reference

Nothing
The subtype of every other type; includes no values

Any
The supertype of any type; any object is of type Any

AnyRef
The supertype of any reference type

All the data types listed above are objects. There are no primitive types like in Java. This means that you can call methods on an Int, Long, etc.

Scala Basic Literals
The rules Scala uses for literals are simple and intuitive

Integral Literals
Integer literals are usually of type Int, or of type Long when followed by a L or l suffix. 
0
035
21
0xFFFFFFFF
0777L

Floating Point Literal:
Floating point literals are of type Float when followed by a floating point type suffix F or f, and are of type Double otherwise. 
0.0
1e30f
3.14159f
1.0e100
.1

Boolean Literals
The Boolean literals true and false are members of type Boolean.
Symbol Literals
A symbol literal 'x is a shorthand for the expression scala.Symbol("x"). Symbol is a case class, which is defined as follows.

package scala
final case class Symbol private (name: String) {
override def toString: String = "'" + name
}


Character Literals
A character literal is a single character enclosed in quotes. The character is either a printable Unicode character or is described by an escape sequence.
'a'
'\u0041'
'\n'
'\t'


String Literals
A string literal is a sequence of characters in double quotes. The characters are either printable Unicode character or are described by escape sequences.
"Hello,\nWorld!"
"This string contains a \" character."

Multi-Line Strings
A multi-line string literal is a sequence of characters enclosed in triple quotes """ ... """. The sequence of characters is arbitrary, except that it may contain three or more consecutive quote characters only at the very end.

Characters must not necessarily be printable; newlines or other control characters are also permitted.

"""the present string
spans three
lines."""


Null Values
The null value is of type scala.Null and is thus compatible with every reference type. It denotes a reference value which refers to a special "null" object.

Escape Sequences
\b	\u0008	backspace BS
\t	\u0009	horizontal tab HT
\n	\u000c	formfeed FF
\f	\u000c	formfeed FF
\r	\u000d	carriage return CR
\"	\u0022	double quote "
\'	\u0027	single quote .
\\	\u005c	backslash \
A character with Unicode between 0 and 255 may also be represented by an octal escape, i.e., a backslash '\' followed by a sequence of up to three octal characters.


object Test {
   def main(args: Array[String]) {
      println("Hello\tWorld\n\n" );
   }
} 


Scala - Variables
Variables are nothing but reserved memory locations to store values. This means that when you create a variable, you reserve some space in memory.

Based on the data type of a variable, the compiler allocates memory and decides what can be stored in the reserved memory. Therefore, by assigning different data types to variables, you can store integers, decimals, or characters in these variables.

Variable Declaration
Scala has a different syntax for declaring variables. They can be defined as value, i.e., constant or a variable. Here, myVar is declared using the keyword var. It is a variable that can change value and this is called mutable variable. Following is the syntax to define a variable using var keyword −

Syntax
var myVar : String = "Foo"
Here, myVal is declared using the keyword val. This means that it is a variable that cannot be changed and this is called immutable variable.

val myVal : String = "Foo"

Variable Data Types
The type of a variable is specified after the variable name and before equals sign. You can define any type of Scala variable by mentioning its data type as follows −
val or val VariableName : DataType = [Initial Value]

If you do not assign any initial value to a variable, then it is valid as follows
var myVar :Int;
val myVal :String;

Variable Type Inference
When you assign an initial value to a variable, the Scala compiler can figure out the type of the variable based on the value assigned to it. This is called variable type inference. Therefore, you could write these variable declarations like this −
var myVar = 10;
val myVal = "Hello, Scala!";

 by default, myVar will be Int type and myVal will become String type variable.

Multiple assignments
Scala supports multiple assignments. If a code block or method returns a Tuple (Tuple − Holds collection of Objects of different types), the Tuple can be assigned to a val variable. [Note − We will study Tuples in subsequent chapters.]

val (myVar1: Int, myVar2: String) = Pair(40, "Foo")
And the type inference gets it right −
val (myVar1, myVar2) = Pair(40, "Foo")

The following is an example program that explains the process of variable declaration in Scala. This program declares four variables — two variables are defined with type declaration and remaining two are without type declaration.

object Demo {
   def main(args: Array[String]) {
      var myVar :Int = 10;
      val myVal :String = "Hello Scala with datatype declaration.";
      var myVar1 = 20;
      val myVal1 = "Hello Scala new without datatype declaration.";
      
      println(myVar); println(myVal); println(myVar1); 
      println(myVal1);
   }
}


Variable Scope
Variables in Scala can have three different scopes depending on the place where they are being used. They can exist as fields, as method parameters and as local variables. Below are the details about each type of scope.

Fields
Fields are variables that belong to an object. The fields are accessible from inside every method in the object. Fields can also be accessible outside the object depending on what access modifiers the field is declared with. Object fields can be both mutable and immutable types and can be defined using either var or val.

Method Parameters
Method parameters are variables, which are used to pass the value inside a method, when the method is called. Method parameters are only accessible from inside the method but the objects passed in may be accessible from the outside, if you have a reference to the object from outside the method. Method parameters are always immutable which are defined by val keyword.

Local Variables
Local variables are variables declared inside a method. Local variables are only accessible from inside the method, but the objects you create may escape the method if you return them from the method. Local variables can be both mutable and immutable types and can be defined using either var or val.


Classes & Objects:
A class is a blueprint for objects. Once you define a class, you can create objects from the class blueprint with the keyword new. Through the object you can use all functionalities of the defined class.


 Class is a blue print and objects are real here. 
Basic Class:
Following is a simple syntax to define a basic class in Scala. This class defines two variables x and y and a method: move, which does not return a value. Class variables are called, fields of the class and methods are called class methods.

The class name works as a class constructor which can take a number of parameters. The above code defines two constructor arguments, xc and yc; they are both visible in the whole body of the class.

class Point(xc: Int, yc: Int) {
var x: Int = xc
var y: Int = yc

def move(dx: Int, dy: Int) {
x = x + dx
y = y + dy
println ("Point x location : " + x);
println ("Point y location : " + y);
}
}


As mentioned earlier in this chapter, you can create objects using a keyword new and then you can access class fields and methods as shown below in the example −

object Demo{
  def main(args:Array[String]): Unit ={
    val pt=new Point(10,20)
    pt.move(20,10);
    
  }
}


Extending a Class
You can extend a base Scala class and you can design an inherited class in the same way you do it in Java (use extends key word), but there are two restrictions: method overriding requires the override keyword, and only the primary constructor can pass parameters to the base constructor. Let us extend our above class and add one more class method.


Example
Let us take an example of two classes Point class (as same example as above) and Location class is inherited class using extends keyword. Such an ‘extends’ clause has two effects: it makes Location class inherit all non-private members from Point class, and it makes the type Location a subtype of the type Point class. So here the Point class is called superclass and the class Location is called subclass. Extending a class and inheriting all the features of a parent class is called inheritance but Scala allows the inheritance from just one class only.

Note − Methods move() method in Point class and move() method in Location class do not override the corresponding definitions of move since they are different definitions (for example, the former take two arguments while the latter take three arguments).


class Location(override val xc: Int, override val yc: Int,
   val zc :Int) extends Point(xc, yc){
   var z: Int = zc

   def move(dx: Int, dy: Int, dz: Int) {
      x = x + dx
      y = y + dy
      z = z + dz
      println ("Point x location : " + x);
      println ("Point y location : " + y);
      println ("Point z location : " + z);
   }
}


Implicit Classes
Implicit classes allow implicit conversations with class’s primary constructor when the class is in scope. Implicit class is a class marked with ‘implicit’ keyword. This feature is introduced in Scala 2.10.

Syntax − The following is the syntax for implicit classes. Here implicit class is always in the object scope where all method definitions are allowed because implicit class cannot be a top level class.

Syntax
object <object name> {
   implicit class <class name>(<Variable>: Data type) {
      def <method>(): Unit =
   }
}


Let us take an example of an implicit class named IntTimes with the method times(). It means the times () contain a loop transaction that will execute the given statement in number of times that we give. Let us assume the given statement is “4 times println (“Hello”)” means the println (“”Hello”) statement will execute 4 times.

The following is the program for the given example. In this example two object classes are used (Run and Demo) so that we have to save those two classes in different files with their respective names as follows.



object Run {
   implicit class IntTimes(x: Int) {
      def times [A](f: =>A): Unit = {
         def loop(current: Int): Unit =
         
         if(current > 0){
            f
            loop(current - 1)
         }
         loop(x)
      }
   }
}

import Run._

object Demo {
   def main(args: Array[String]) {
      4 times println("hello")
   }
}


Note −

Implicit classes must be defined inside another class/object/trait (not in top level).

Implicit classes may only take one non –implicit argument in their constructor.

Implicit classes may not be any method, member or object in scope with the same name as the implicit class.



Singleton Objects
Scala is more object-oriented than Java because in Scala, we cannot have static members. Instead, Scala has singleton objects. A singleton is a class that can have only one instance, i.e., Object. You create singleton using the keyword object instead of class keyword. Since you can't instantiate a singleton object, you can't pass parameters to the primary constructor. You already have seen all the examples using singleton objects where you called Scala's main method.


object SingletonDemo{
  def main(args:Array[String]): Unit ={
    val point=new Point(10,20)
    printPoint

    def printPoint: Unit ={
      println(point.x)
      println(point.y)
    }
  }
}


Access Modifiers:
 Members of packages, classes or objects can be labeled with the access modifiers private and protected, and if we are not using either of these two keywords, then access will be assumed as public. These modifiers restrict accesses to the members to certain regions of code. To use an access modifier, you include its keyword in the definition of members of package, class or object as we will see in the following section.

Private Members

A private member is visible only inside the class or object that contains the member definition.


class Outer{
  class Inner{
    private def f(): Unit ={
      println("f")
    }

    class InnerMost{
      f()//OK
    }
  }

//  (new Inner).f()
  // Error: f is not accessible
}



In Scala, the access (new Inner). f() is illegal because f is declared private in Inner and the access is not from within class Inner. By contrast, the first access to f in class Innermost is OK, because that access is contained in the body of class Inner. Java would permit both accesses because it lets an outer class access private members of its inner classes.


Protected Members
A protected member is only accessible from subclasses of the class in which the member is defined.


package p{

  class Super{
    protected  def f():Unit={
      println("F")}

  }

  class Sub extends Super{
    f()
  }

  class Other{
//    (new Super).f() 
    //// Error: f is not accessible
  }
}

The access to f in class Sub is OK because f is declared protected in ‘Super’ class and ‘Sub’ class is a subclass of Super. By contrast the access to f in ‘Other’ class is not permitted, because class ‘Other’ does not inherit from class ‘Super’. In Java, the latter access would be still permitted because ‘Other’ class is in the same package as ‘Sub’ class.

Public Members





```
