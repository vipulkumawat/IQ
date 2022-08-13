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


```
