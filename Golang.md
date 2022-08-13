**GoLang**

Go language is a programming language initially developed at Google in the year 2007.  
It provides garbage collection, type safety, dynamic-typing capability, many advanced built-in types such as variable length arrays and key-value maps. general-purpose language designed with systems programming in mind. strongly and statically typed, provides inbuilt support for garbage collection, and supports concurrent programming. Programs are constructed using packages, for efficient management of dependencies. Go programming implementations use a traditional compile and link model to generate executable binaries. 
```
The most important features of Go programming are listed below −

Support for environment adopting patterns similar to dynamic languages. For example, type inference (x := 0 is valid declaration of a variable x of type int)
Compilation time is fast.
Inbuilt concurrency support: lightweight processes (via go routines), channels, select statement.
Go programs are simple, concise, and safe.
Support for Interfaces and Type embedding.
Production of statically linked native binaries without external dependencies.

Features Excluded Intentionally
To keep the language simple and concise, the following features commonly available in other similar languages are omitted in Go −
Support for type inheritance
Support for method or operator overloading
Support for circular dependencies among packages
Support for pointer arithmetic
Support for assertions
Support for generic programming
```

```
Strong and statically typed
strong typing means type of a variable cannot change over time.
statically typed means all of those variables have to be defined at compile time.

key features:
simplicity to learn
fast compile times
garbage collected language means you don't have to manage memory, go runtime is going to manage that for you.why? garbage collected language does have challengees when dealing with certain usecases. ex: realtime trading systems for stock market systems have a very hard time when you're dealing with garbage collection.
Built-in concurrency: have concurrency primitives built right into the language. instead of having a library that we're going to have to import, inorder to work with concurrency, we are going to do concurrent development right there in the base language.
compile to standalone library: compiles down to a standalone library which means when you compile your go application, everything is going to be bundled into the single binary that's related to the go application.
version management at runtime becomes trivial as you simply have one binary, you deploy that binary, you run it and all of its dependencies are there.


golang.org
golang.org/doc/effective_go.html

https://www.youtube.com/watch?v=YS4e4q9oBaU
17:00	

The source code written in source file is the human readable source for your program. It needs to be compiled and turned into machine language so that your CPU can actually execute the program as per the instructions given. The Go programming language compiler compiles the source code into its final executable program.

go1.4.windows-amd64.msi
 set the c:\Go\bin directory in Window's PATH environment variable. Restart any open command prompts for the change to take effect.

test.go:
package main
import "fmt"

func main(){
   fmt.Println("Hello World")
}

execution: go run test.go

error when I run with .txt file:
no required module provides package test.txt: go.mod file not found in current directory or any parent directory; see 'go help modules




let us first discuss the bare minimum structure of Go programs so that we can take it as a reference in subsequent chapters.

Hello World Example
A Go program basically consists of the following parts −

Package Declaration
Import Packages
Functions
Variables
Statements and Expressions
Comments


The first line of the program package main defines the package name in which this program should lie. It is a mandatory statement, as Go programs run in packages. The main package is the starting point to run the program. Each package has a path and name associated with it.

The next line import "fmt" is a preprocessor command which tells the Go compiler to include the files lying in the package fmt.

The next line func main() is the main function where the program execution begins.

The next line /*...*/ is ignored by the compiler and it is there to add comments in the program. Comments are also represented using // similar to Java or C++ comments.

The next line fmt.Println(...) is another function available in Go which causes the message "Hello, World!" to be displayed on the screen. Here fmt package has exported Println method which is used to display the message on the screen.

Notice the capital P of Println method. In Go language, a name is exported if it starts with capital letter. Exported means the function or variable/constant is accessible to the importer of the respective package.


Executing a Go Program:
go run hello.go

Tokens in Go
A Go program consists of various tokens. A token is either a keyword, an identifier, a constant, a string literal, or a symbol. For example, the following Go statement consists of six tokens −

fmt.Println("Hello, World!")
The individual tokens are −

fmt
.
Println
(
   "Hello, World!"
)

In a Go program, the line separator key is a statement terminator. 
That is, individual statements don't need a special separator like “;” in C. 
The Go compiler internally places “;” as the statement terminator to indicate the end of one logical entity.

ex usage:
fmt.Println("Hello, World!")
fmt.Println("I am in Go Programming World!")



Comments
Comments are like helping texts in your Go program and they are ignored by the compiler. They start with /* and terminates with the characters */ as shown below −

/* my first program in Go */
You cannot have comments within comments and they do not occur within a string or character literals.

Identifiers:
 An identifier starts with a letter A to Z or a to z or an underscore _ followed by zero or more letters, underscores, and digits (0 to 9).
identifier = letter { letter | unicode_digit }.

Go does not allow punctuation characters such as @, $, and % within identifiers. Go is a case-sensitive programming language. Thus, Manpower and manpower are two different identifiers in Go.

Keywords:

break | default | func | interface | select
case | defer | Go | map | Struct
chan | else | Goto | package | Switch
const | fallthrough | if | range | Type
continue | for | import | return | Var


Go - Data Types:
data types refer to an extensive system used for declaring variables or functions of different types. The type of a variable determines how much space it occupies in storage and how the bit pattern stored is interpreted.

Boolean types: true or false
Numeric types: integer and floating point
String types: represents the set of string values. Its value is a sequence of bytes. 
Strings are immutable types that is once created, it is not possible to change the contents of a string.
 The predeclared string type is string.

Derived types
They include 
(a) Pointer types, 
(b) Array types, 
(c) Structure types, 
(d) Union types and 
(e) Function types 
f) Slice types
 g) Interface types
 h) Map types
 i) Channel Types



Array types and structure types are collectively referred to as aggregate types. 
The type of a function specifies the set of all functions with the same parameter and result types.

Integer types:
uint8: (0 to 255)
uint16: (0 to 65535)
uint32:  (0 to 4294967295)
uint64: (0 to 18446744073709551615)
int8: (-128 to 127)
int16:  (-32768 to 32767)
int32:  (-2147483648 to 2147483647)
int64: (-9223372036854775808 to 9223372036854775807)

Floating types:
float32: IEEE-754 32-bit floating-point numbers
float64: IEEE-754 64-bit floating-point numbers
complex64: Complex numbers with float32 real and imaginary parts
complex128: Complex numbers with float64 real and imaginary parts


The value of an n-bit integer is n bits and is represented using two's complement arithmetic operations.


other numeric types:
byte: same as uint8
rune: same as int32
uint: 32 or 64 bits
int: same size as uint
uintptr: an unsigned integer to store the uninterpreted bits of a pointer value


Go - Variables

A variable is nothing but a name given to a storage area that the programs can manipulate. Each variable in Go has a specific type, which determines the size and layout of the variable's memory, the range of values that can be stored within that memory, and the set of operations that can be applied to the variable.

The name of a variable can be composed of letters, digits, and the underscore character. It must begin with either a letter or an underscore. Upper and lowercase letters are distinct because Go is case-sensitive. Based on the basic types explained in the previous chapter, there will be the following basic variable types −


byte: Typically a single octet(one byte). This is an byte type.
int: The most natural size of integer for the machine.
float32: A single-precision floating point value


Go programming language also allows to define various other types of variables such as 
Enumeration, Pointer, Array, Structure, and Union, which we will discuss in subsequent chapters. 

Variable Definition in Go
A variable definition tells the compiler where and how much storage to create for the variable. A variable definition specifies a data type and contains a list of one or more variables of that type as follows −

var variable_list optional_data_type;
Here, optional_data_type is a valid Go data type including byte, int, float32, complex64, boolean or any user-defined object, etc., and variable_list may consist of one or more identifier names separated by commas. Some valid declarations are shown here −

var i, j, k int;
var c, ch byte;
var f, salary float32;
d = 42;



The statement “var i, j, k;” declares and defines the variables i, j and k; which instructs the compiler to create variables named i, j, and k of type int.

Variables can be initialized (assigned an initial value) in their declaration. The type of variable is automatically judged by the compiler based on the value passed to it. The initializer consists of an equal sign followed by a constant expression as follows −

variable_name = value;
For example,

d = 3, f = 5;


For definition without an initializer: variables with static storage duration are implicitly initialized with nil (all bytes have the value 0); the initial value of all other variables is zero value of their data type.

Static Type Declaration in Go
A static type variable declaration provides assurance to the compiler that there is one variable available with the given type and name so that the compiler can proceed for further compilation without requiring the complete detail of the variable. A variable declaration has its meaning at the time of compilation only, the compiler needs the actual variable declaration at the time of linking of the program.
#program test1.go




Dynamic Type Declaration / Type Inference in Go
A dynamic type variable declaration requires the compiler to interpret the type of the variable based on the value passed to it. The compiler does not require a variable to have type statically as a necessary requirement.

for dynamic type inference use := operator

#test2.go


Mixed Variable Declaration in Go
Variables of different types can be declared in one go using type inference.

#test3.go

The lvalues and the rvalues in Go
There are two kinds of expressions in Go −

lvalue − Expressions that refer to a memory location is called "lvalue" expression. An lvalue may appear as either the left-hand or right-hand side of an assignment.

rvalue − The term rvalue refers to a data value that is stored at some address in memory. An rvalue is an expression that cannot have a value assigned to it which means an rvalue may appear on the right- but not left-hand side of an assignment.

Variables are lvalues and so may appear on the left-hand side of an assignment. Numeric literals are rvalues and so may not be assigned and can not appear on the left-hand side.

The following statement is valid −
x = 20.0
The following statement is not valid. It would generate compile-time error −
10 = 20


Go - Constants:
Constants refer to fixed values that the program may not alter during its execution. These fixed values are also called literals.

Constants can be of any of the basic data types like an integer constant, a floating constant, a character constant, or a string literal. There are also enumeration constants as well.

Constants are treated just like regular variables except that their values cannot be modified after their definition.

Integer Literals
An integer literal can be a decimal, octal, or hexadecimal constant. A prefix specifies the base or radix: 0x or 0X for hexadecimal, 0 for octal, and nothing for decimal.

An integer literal can also have a suffix that is a combination of U and L, for unsigned and long, respectively. The suffix can be uppercase or lowercase and can be in any order.

Here are some examples of integer literals −

212 /* Legal */
215u /* Legal */
0xFeeL /* Legal */
078 /* Illegal: 8 is not an octal digit */
032UU /* Illegal: cannot repeat a suffix */


Following are other examples of various type of Integer literals −

85 /* decimal */
0213 /* octal */
0x4b /* hexadecimal */
30 /* int */
30u /* unsigned int */
30l /* long */
30ul /* unsigned long */


Floating-point Literals:


A floating-point literal has an integer part, a decimal point, a fractional part, and an exponent part. You can represent floating point literals either in decimal form or exponential form.

While representing using decimal form, you must include the decimal point, the exponent, or both and 
while representing using exponential form, you must include the integer part, the fractional part, or both. 
The signed exponent is introduced by e or E.

Escape Sequence
When certain characters are preceded by a backslash, they will have a special meaning in Go. 
These are known as Escape Sequence codes which are used to represent newline (\n), tab (\t), backspace, etc.



\\, \', \", \?, \a, \b, \f, \n, \r, \t, \v, \ooo, \xhh
#test4.go

String Literals in Go
String literals or constants are enclosed in double quotes "". A string contains characters that are similar to character literals: plain characters, escape sequences, and universal characters.

You can break a long line into multiple lines using string literals and separating them using whitespaces.

Here are some examples of string literals. All the three forms are identical strings.

"hello, dear"

"hello, \

dear"

"hello, " "d" "ear"


The const Keyword
You can use const prefix to declare constants with a specific type as follows −

const variable type = value;

#test5.go

Note that it is a good programming practice to define constants in CAPITALS.


Go - Operators:


Arithmetic Operators:+, -, *, /, %, ++, --
Relational Operators: ==, !=, >, <, >=, <=
Logical Operators: &&, ||, !
Bitwise Operators: &, |, ^, >>, <<
Assignment Operators: =, +=, -=, *=, /=, %=, <<=, >>=, &=, ^=, |=
Miscellaneous Operators: sizeof, ?:, &	Returns the address of a variable., *	Pointer to a variable.


Operators Precedence in Go:
operators with the highest precedence appear at the top of the table, those with the lowest appear at the bottom

Postfix	() [] -> . ++ - -	Left to right
Unary	+ - ! ~ ++ - - (type)* & sizeof	Right to left
Multiplicative	* / %	Left to right
Additive	+ -	Left to right
Shift	<< >>	Left to right
Relational	< <= > >=	Left to right
Equality	== !=	Left to right
Bitwise AND	&	Left to right
Bitwise XOR	^	Left to right
Bitwise OR	|	Left to right
Logical AND	&&	Left to right
Logical OR	||	Left to right
Assignment	= += -= *= /= %=>>= <<= &= ^= |=	Right to left
Comma	,	Left to right

Go - Decision Making
	if statement
if(boolean_expression) {
/* statement(s) will execute if the boolean expression is true */
}

if...else statement:
if(boolean_expression) {
/* statement(s) will execute if the boolean expression is true */
} else {
/* statement(s) will execute if the boolean expression is false */
}

nested if statements

switch statement:
switch(boolean-expression or integral type){
case boolean-expression or integral type :
statement(s);
case boolean-expression or integral type :
statement(s);

/* you can have any number of case statements */
default : /* Optional */
statement(s);
}


A switch statement allows a variable to be tested for equality against a list of values. Each value is called a case, and the variable being switched on is checked for each switch case.

In Go programming, switch statements are of two types −

Expression Switch − In expression switch, a case contains expressions, which is compared against the value of the switch expression.

Type Switch − In type switch, a case contain type which is compared against the type of a specially annotated switch expression.


The following rules apply to a switch statement −

The expression used in a switch statement must have an integral or boolean expression, or be of a class type in which the class has a single conversion function to an integral or boolean value. If the expression is not passed then the default value is true.

You can have any number of case statements within a switch. Each case is followed by the value to be compared to and a colon.

The constant-expression for a case must be the same data type as the variable in the switch, and it must be a constant or a literal.

When the variable being switched on is equal to a case, the statements following that case will execute. No break is needed in the case statement.

A switch statement can have an optional default case, which must appear at the end of the switch. The default case can be used for performing a task when none of the cases is true. No break is needed in the default case.

#test6.go

Type Switch
The syntax for a type switch statement in Go programming is
switch x.(type){

case type:
statement(s);
case type:
statement(s);
/* you can have any number of case statements */
default: /* Optional */
statement(s);

}


The following rules apply to a switch statement −

The expression used in a switch statement must have an variable of interface{} type.

You can have any number of case statements within a switch. Each case is followed by the value to be compared to and a colon.

The type for a case must be the same data type as the variable in the switch, and it must be a valid data type.

When the variable being switched on is equal to a case, the statements following that case will execute. No break is needed in the case statement.

A switch statement can have an optional default case, which must appear at the end of the switch. The default case can be used for performing a task when none of the cases is true. No break is needed in the default case.

#test7.go

select statement:
A select statement is similar to switch statement with difference that case statements refers to channel communications.

syntax for a select statement:
select {
case communication clause :
statement(s);
case communication clause :
statement(s);
/* you can have any number of case statements */
default : /* Optional */
statement(s);
}


The following rules apply to a select statement −
You can have any number of case statements within a select. Each case is followed by the value to be compared to and a colon.
The type for a case must be the a communication channel operation.
When the channel operation occurred the statements following that case will execute. No break is needed in the case statement.
A select statement can have an optional default case, which must appear at the end of the select. The default case can be used for performing a task when none of the cases is true. No break is needed in the default case.

#test8.go

Go - Loops:
for loop-
for [condition | ( init; condition; increment ) | Range] {
statement(s);
}

The flow of control in a for loop is a follows −
If a condition is available, then for loop executes as long as condition is true.
If a for clause that is ( init; condition; increment ) is present then −
The init step is executed first, and only once. This step allows you to declare and initialize any loop control variables. You are not required to put a statement here, as long as a semicolon appears.
Next, the condition is evaluated. If it is true, the body of the loop is executed. If it is false, the body of the loop does not execute and the flow of control jumps to the next statement just after the for loop.
After the body of the for loop executes, the flow of control jumps back up to the increment statement. This statement allows you to update any loop control variables. This statement can be left blank, as long as a semicolon appears after the condition.
The condition is now evaluated again. If it is true, the loop executes and the process repeats itself (body of loop, then increment step, and then again the condition). After the condition becomes false, the for loop terminates.


If range is available, then the for loop executes for each item in the range.

#test9.go

nested loops:
These are one or multiple loops inside any for loop.

 syntax for a nested for loop :

for [condition | ( init; condition; increment ) | Range] {
for [condition | ( init; condition; increment ) | Range] {
statement(s);
}
statement(s);
}


#test10.go

Loop Control Statements:
https://www.tutorialspoint.com/go/go_loops.htm






```
