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


```
https://www.tutorialspoint.com/go/go_environment.htm