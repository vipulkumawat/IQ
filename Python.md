**Python:**
Python is a high-level, interpreted, interactive and object-oriented scripting language.
```
Python is Interpreted − Python is processed at runtime by the interpreter. You do not need to compile your program before executing it. This is similar to PERL and PHP.

Python is Interactive − You can actually sit at a Python prompt and interact with the interpreter directly to write your programs.

Python is Object-Oriented − Python supports Object-Oriented style or technique of programming that encapsulates code within objects.

Python is a Beginner's Language − Python is a great language for the beginner-level programmers and supports the development of a wide range of applications from simple text processing to WWW browsers to games.
It supports functional and structured programming methods as well as OOP.
It can be used as a scripting language or can be compiled to byte-code for building large applications.
It provides very high-level dynamic data types and supports dynamic type checking.
It supports automatic garbage collection.
It can be easily integrated with C, C++, COM, ActiveX, CORBA, and Java.
steps to install Python on Windows machine.
Open a Web browser and go to https://www.python.org/downloads
Setting up PATH:
Add to environment variable python home folder path


Python Environment Variables
Here are important environment variables, which can be recognized by Python −

PYTHONPATH
It has a role similar to PATH. This variable tells the Python interpreter where to locate the module files imported into a program. It should include the Python source library directory and the directories containing Python source code. PYTHONPATH is sometimes preset by the Python installer.

PYTHONSTARTUP
It contains the path of an initialization file containing Python source code. It is executed every time you start the interpreter. It is named as .pythonrc.py in Unix and it contains commands that load utilities or modify PYTHONPATH.

PYTHONCASEOK
It is used in Windows to instruct Python to find the first case-insensitive match in an import statement. Set this variable to any value to activate it.

PYTHONHOME
It is an alternative module search path. It is usually embedded in the PYTHONSTARTUP or PYTHONPATH directories to make switching module libraries easy.

There are three different ways to start Python −
Interactive Interpreter
You can start Python from Unix, DOS, or any other system that provides you a command-line interpreter or shell window.


list of all the available command line options 
-d
It provides debug output.

-O
It generates optimized bytecode (resulting in .pyo files).

-S
Do not run import site to look for Python paths on startup.

-v
verbose output (detailed trace on import statements).

-X
disable class-based built-in exceptions (just use strings); obsolete starting with version 1.6.

-c cmd
run Python script sent in as cmd string

file
run Python script from given file

Script from the Command-line
A Python script can be executed at command line by invoking the interpreter on your application

Integrated Development Environment
You can run Python from a Graphical User Interface (GUI) environment as well, if you have a GUI application on your system that supports Python.

Unix − IDLE is the very first Unix IDE for Python.

Windows − PythonWin is the first Windows interface for Python and is an IDE with a GUI.

Macintosh − The Macintosh version of Python along with the IDLE IDE is available from the main website, downloadable as either MacBinary or BinHex'd files.

Script Mode Programming
Invoking the interpreter with a script parameter begins execution of the script and continues until the script is finished. When the script is finished, the interpreter is no longer active.


Python Identifiers
A Python identifier is a name used to identify a variable, function, class, module or other object. An identifier starts with a letter A to Z or a to z or an underscore (_) followed by zero or more letters, underscores and digits (0 to 9).

Python does not allow punctuation characters such as @, $, and % within identifiers. Python is a case sensitive programming language. Thus, Manpower and manpower are two different identifiers in Python.

**Here are naming conventions for Python identifiers −**

Class names start with an uppercase letter. All other identifiers start with a lowercase letter.
Starting an identifier with a single leading underscore indicates that the identifier is private.
Starting an identifier with two leading underscores indicates a strongly private identifier.
If the identifier also ends with two trailing underscores, the identifier is a language-defined special name.

Reserved Words
The following list shows the Python keywords. These are reserved words and you cannot use them as constant or variable or any other identifier names. All the Python keywords contain lowercase letters only.

and	exec	not
assert	finally	or
break	for	pass
class	from	print
continue	global	raise
def	if	return
del	import	try
elif	in	while
else	is	with
except	lambda	yield


Lines and Indentation
Python provides no braces to indicate blocks of code for class and function definitions or flow control. Blocks of code are denoted by line indentation, which is rigidly enforced.
The number of spaces in the indentation is variable, but all statements within the block must be indented the same amount.

in Python all the continuous lines indented with same number of spaces would form a block. 

Multi-Line Statements
Statements in Python typically end with a new line. Python does, however, allow the use of the line continuation character (\) to denote that the line should continue.

total = item_one + \
        item_two + \
        item_three
Statements contained within the [], {}, or () brackets do not need to use the line continuation character. For example −

days = ['Monday', 'Tuesday', 'Wednesday',
        'Thursday', 'Friday']
Quotation in Python
Python accepts single ('), double (") and triple (''' or """) quotes to denote string literals, as long as the same type of quote starts and ends the string.

The triple quotes are used to span the string across multiple lines. For example, all the following are legal −

word = 'word'
sentence = "This is a sentence."
paragraph = """This is a paragraph. It is
made up of multiple lines and sentences."""
Comments in Python
A hash sign (#) that is not inside a string literal begins a comment. All characters after the # and up to the end of the physical line are part of the comment and the Python interpreter ignores them.

# First comment
print "Hello, Python!" # second comment

Following triple-quoted string is also ignored by Python interpreter and can be used as a multiline comments:

'''
This is a multiline
comment.
'''

Waiting for the User
The following line of the program displays the prompt, the statement saying “Press the enter key to exit”, and waits for the user to take action −

#!/usr/bin/python

raw_input("\n\nPress the enter key to exit.")

Once the user presses the key, the program ends. This is a nice trick to keep a console window open until the user is done with an application.

Multiple Statements on a Single Line
The semicolon ( ; ) allows multiple statements on the single line given that neither statement starts a new code block. 


Multiple Statement Groups as Suites
A group of individual statements, which make a single code block are called suites in Python. Compound or complex statements, such as if, while, def, and class require a header line and a suite.

Header lines begin the statement (with the keyword) and terminate with a colon ( : ) and are followed by one or more lines which make up the suite. For example −

if expression : 
   suite
elif expression : 
   suite 
else : 
   suite
Command Line Arguments
Many programs can be run to provide you with some basic information about how they should be run. Python enables you to do this with -h −

$ python -h
usage: python [option] ... [-c cmd | -m mod | file | -] [arg] ...
Options and arguments (and corresponding environment variables):
-c cmd : program passed in as string (terminates option list)
-d     : debug output from parser (also PYTHONDEBUG=x)
-E     : ignore environment variables (such as PYTHONPATH)
-h     : print this help message and exit

```
**Variable Types:**
```
Variables are nothing but reserved memory locations to store values. This means that when you create a variable you reserve some space in memory.

Based on the data type of a variable, the interpreter allocates memory and decides what can be stored in the reserved memory. Therefore, by assigning different data types to variables, you can store integers, decimals or characters in these variables.

Python variables do not need explicit declaration to reserve memory space. The declaration happens automatically when you assign a value to a variable. The equal sign (=) is used to assign values to variables.

The operand to the left of the = operator is the name of the variable and the operand to the right of the = operator is the value stored in the variable. For example −

Live Demo
#!/usr/bin/python

counter = 100          # An integer assignment
miles   = 1000.0       # A floating point
name    = "John"       # A string


Multiple Assignment
Python allows you to assign a single value to several variables simultaneously. For example −

a = b = c = 1
Here, an integer object is created with the value 1, and all three variables are assigned to the same memory location. You can also assign multiple objects to multiple variables. For example −

a,b,c = 1,2,"john"
Here, two integer objects with values 1 and 2 are assigned to variables a and b respectively, and one string object with the value "john" is assigned to the variable c.

Standard Data Types
The data stored in memory can be of many types. For example, a person's age is stored as a numeric value and his or her address is stored as alphanumeric characters. Python has various standard data types that are used to define the operations possible on them and the storage method for each of them.

Python has five standard data types −

Numbers
String
List
Tuple
Dictionary


Python Numbers
Number data types store numeric values. Number objects are created when you assign a value to them. For example −

var1 = 1
var2 = 10
You can also delete the reference to a number object by using the del statement. The syntax of the del statement is −

del var1[,var2[,var3[....,varN]]]]
You can delete a single object or multiple objects by using the del statement. For example −

del var
del var_a, var_b
Python supports four different numerical types −

int (signed integers) 100, -9889,080, -0490, 0x260, 0x69
long (long integers, they can also be represented in octal and hexadecimal) 51924361L, -0x19323L, 0xDEFABCECBDAECBFBAEl, -4721885298529L
float (floating point real values) 0.0, -21.9, 32.3+e18, -90., 70.2-E12
complex (complex numbers) 3.14j, 9.322e-36j, .876j, 4.53e-7j

tutorialspoint.com/python/python_variable_types.htm
Python allows you to use a lowercase l with long, but it is recommended that you use only an uppercase L to avoid confusion with the number 1. Python displays long integers with an uppercase L.

A complex number consists of an ordered pair of real floating-point numbers denoted by x + yj, where x and y are the real numbers and j is the imaginary unit.

Python Strings
Strings in Python are identified as a contiguous set of characters represented in the quotation marks. Python allows for either pairs of single or double quotes. Subsets of strings can be taken using the slice operator ([ ] and [:] ) with indexes starting at 0 in the beginning of the string and working their way from -1 at the end.

The plus (+) sign is the string concatenation operator and the asterisk (*) is the repetition operator.

str = 'Hello World!'

print str          # Prints complete string
print str[0]       # Prints first character of the string
print str[2:5]     # Prints characters starting from 3rd to 5th
print str[2:]      # Prints string starting from 3rd character
print str * 2      # Prints string two times
print str + "TEST" # Prints concatenated string
This will produce the following result −

Hello World!
H
llo
llo World!
Hello World!Hello World!
Hello World!TEST

Python Lists:
Lists are the most versatile of Python's compound data types.
A list contains items separated by commas and enclosed within square brackets ([]). 
To some extent, lists are similar to arrays in C.
One difference between them is that all the items belonging to a list can be of different data type.

The values stored in a list can be accessed using the slice operator ([ ] and [:]) with indexes starting at 0 in the beginning of the list and working their way to end -1. 
The plus (+) sign is the list concatenation operator, and the asterisk (*) is the repetition operator. 

list = [ 'abcd', 786 , 2.23, 'john', 70.2 ]
tinylist = [123, 'john']
print list          # Prints complete list
print list[0]       # Prints first element of the list
print list[1:3]     # Prints elements starting from 2nd till 3rd 
print list[2:]      # Prints elements starting from 3rd element
print tinylist * 2  # Prints list two times
print list + tinylist # Prints concatenated lists


Python Tuples
A tuple is another sequence data type that is similar to the list. A tuple consists of a number of values separated by commas. Unlike lists, however, tuples are enclosed within parentheses.

The main differences between lists and tuples are: Lists are enclosed in brackets ( [ ] ) and their elements and size can be changed, while tuples are enclosed in parentheses ( ( ) ) and cannot be updated. Tuples can be thought of as read-only lists.


tuple = ( 'abcd', 786 , 2.23, 'john', 70.2  )
tinytuple = (123, 'john')

print tuple               # Prints the complete tuple
print tuple[0]            # Prints first element of the tuple
print tuple[1:3]          # Prints elements of the tuple starting from 2nd till 3rd 
print tuple[2:]           # Prints elements of the tuple starting from 3rd element
print tinytuple * 2       # Prints the contents of the tuple twice
print tuple + tinytuple   # Prints concatenated tuples



The following code is invalid with tuple, because we attempted to update a tuple, which is not allowed. Similar case is possible with lists −

#!/usr/bin/python

tuple = ( 'abcd', 786 , 2.23, 'john', 70.2  )
list = [ 'abcd', 786 , 2.23, 'john', 70.2  ]
tuple[2] = 1000    # Invalid syntax with tuple
list[2] = 1000     # Valid syntax with list



Python Dictionary
Python's dictionaries are kind of hash table type. They work like associative arrays or hashes found in Perl and consist of key-value pairs. A dictionary key can be almost any Python type, but are usually numbers or strings. Values, on the other hand, can be any arbitrary Python object.

Dictionaries are enclosed by curly braces ({ }) and values can be assigned and accessed using square braces ([]). For example −

#!/usr/bin/python

dict = {}
dict['one'] = "This is one"
dict[2]     = "This is two"

tinydict = {'name': 'john','code':6734, 'dept': 'sales'}


print dict['one']       # Prints value for 'one' key
print dict[2]           # Prints value for 2 key
print tinydict          # Prints complete dictionary
print tinydict.keys()   # Prints all the keys
print tinydict.values() # Prints all the values



Dictionaries have no concept of order among elements. It is incorrect to say that the elements are "out of order"; they are simply unordered.
Data Type Conversion
Sometimes, you may need to perform conversions between the built-in types. To convert between types, you simply use the type name as a function.

There are several built-in functions to perform conversion from one data type to another. These functions return a new object representing the converted value.


int(x [,base]) Converts x to an integer. base specifies the base if x is a string.
long(x [,base] ) Converts x to a long integer. base specifies the base if x is a string.
float(x) Converts x to a floating-point number.
complex(real [,imag]) Creates a complex number.
str(x) Converts object x to a string representation.
repr(x) Converts object x to an expression string.
eval(str) Evaluates a string and returns an object.
tuple(s) Converts s to a tuple.
list(s) Converts s to a list.
set(s) Converts s to a set.
dict(d) Creates a dictionary. d must be a sequence of (key,value) tuples.
frozenset(s) Converts s to a frozen set.
chr(x) Converts an integer to a character.
unichr(x) Converts an integer to a Unicode character.
ord(x) Converts a single character to its integer value.
hex(x) Converts an integer to a hexadecimal string.
oct(x) Converts an integer to an octal string.


Python - Basic Operators:
Types of Operator
Python language supports the following types of operators.

Arithmetic Operators
Comparison (Relational) Operators
Assignment Operators
Logical Operators
Bitwise Operators
Membership Operators
Identity Operators

Arithmetic Operators:
+,-,*,/,%,**(exponent),//(floor division)
The division of operands where the result is the quotient in which the digits after the decimal point are removed. But if one of the operands is negative, the result is floored, i.e., rounded away from zero (towards negative infinity)
9//2 = 4 and 9.0//2.0 = 4.0, -11//3 = -4, -11.0//3 = -4.0

Comparison Operators:
These operators compare the values on either sides of them and decide the relation among them.
==, !=, <>(similar to != operator), >, <, >=, <=

Assignment Operators
=, +=(Add And), -=(subtract And), *=(multiply And), /= (Divide And), %=(Modulus AND), **=(Exponent AND), //=(floor Division) 

Bitwise Operators:
Bitwise operator works on bits and performs bit by bit operation
 if a = 60; and b = 13; Now in the binary format their values will be 0011 1100 and 0000 1101 respectively
a = 0011 1100

b = 0000 1101

-----------------

a&b = 0000 1100

a|b = 0011 1101

a^b = 0011 0001

~a  = 1100 0011


& Binary AND
| Binary OR
^ Binary XOR
~ BinaryOnesComplement
<< Binary Left Shift
The left operands value is moved left by the number of bits specified by the right operand.
a << 2 = 240 (means 1111 0000)
>> Binary Right Shift
The left operands value is moved right by the number of bits specified by the right operand.
a >> 2 = 15 (means 0000 1111)


Logical Operators:
and: Logical AND
If both the operands are true then condition becomes true.
or: Logical OR
If any of the two operands are non-zero then condition becomes true.
not: Logical NOT
Used to reverse the logical state of its operand.

Membership Operators:
membership operators test for membership in a sequence, such as strings, lists, or tuples
in: 
Evaluates to true if it finds a variable in the specified sequence and false otherwise.
x in y, here in results in a 1 if x is a member of sequence y.

not in:
Evaluates to true if it does not finds a variable in the specified sequence and false otherwise.
x not in y, here not in results in a 1 if x is not a member of sequence y.


Identity Operators:
Identity operators compare the memory locations of two objects.
is: Evaluates to true if the variables on either side of the operator point to the same object and false otherwise.
x is y, here is results in 1 if id(x) equals id(y).
is not: Evaluates to false if the variables on either side of the operator point to the same object and true otherwise.
x is not y, here is not results in 1 if id(x) is not equal to id(y).

Operator Precedence:
** Exponentiation (raise to the power)
~+- Complement, unary plus and minus (method names for the last two are +@ and -@)
* / % // Multiply, divide, modulo and floor division
+ - Addition and subtraction
>> << Right and left bitwise shift
& Bitwise 'AND'
^| Bitwise exclusive `OR' and regular `OR'
<= < > >= Comparison operators
<> == != Equality operators
= %= /= //= -= += *= **= Assignment operators
is is not Identity operators
in not in Membership operators
not or and Logical operators



Python - Decision Making:
Decision making is anticipation of conditions occurring while execution of the program and specifying actions taken according to the conditions.

Decision structures evaluate multiple expressions which produce TRUE or FALSE as outcome. You need to determine which action to take and which statements to execute if outcome is TRUE or FALSE otherwise.

if
if...else
nested if

#!/usr/bin/python
var=100
if(var==100):
print "Value of expression is 100"
print "Good bye!"


Python Loops:
when you need to execute a block of code several number of times.

while loop
for loop
nested loops


break statement
continue statement
pass statement

Python - Numbers:
Number data types store numeric values. They are immutable data types, means that changing the value of a number data type results in a newly allocated object.
Number objects are created when you assign a value to them. For example −

var1 = 1
var2 = 10
You can also delete the reference to a number object by using the del statement.

del var1[,var2[,var3[....,varN]]]]

Python supports four different numerical types:
int:(signed integers) − They are often called just integers or ints, are positive or negative whole numbers with no decimal point.
long: (long integers ) − Also called longs, they are integers of unlimited size, written like integers and followed by an uppercase or lowercase L.
float: (floating point real values) − Also called floats, they represent real numbers and are written with a decimal point dividing the integer and fractional parts. Floats may also be in scientific notation, with E or e indicating the power of 10 (2.5e2 = 2.5 x 102 = 250).
complex:(complex numbers) − are of the form a + bJ, where a and b are floats and J (or j) represents the square root of -1 (which is an imaginary number). The real part of the number is a, and the imaginary part is b. Complex numbers are not used much in Python programming.


Python allows you to use a lowercase L with long, but it is recommended that you use only an uppercase L to avoid confusion with the number 1. Python displays long integers with an uppercase L.

A complex number consists of an ordered pair of real floating point numbers denoted by a + bj, where a is the real part and b is the imaginary part of the complex number.

Number Type Conversion:
Python converts numbers internally in an expression containing mixed types to a common type for evaluation. But sometimes, you need to coerce a number explicitly from one type to another to satisfy the requirements of an operator or function parameter.
int(x) to convert x to a plain integer.
long(x) to convert x to a long integer.
float(x) to convert x to a floating-point number.
complex(x) to convert x to a complex number with real part x and imaginary part zero.
complex(x, y) to convert x and y to a complex number with real part x and imaginary part y. x and y are numeric expressions

Mathematical Functions:
abs(x):The absolute value of x: the (positive) distance between x and zero.
ceil(x): the smallest integer not less than x
cmp(x,y): -1 if x < y, 0 if x == y, or 1 if x > y
exp(x):  exponential of x
fabs(x):absolute value of x
floor(x): the largest integer not greater than x
log(x): natural logarithm of x, for x> 0
log10(x): base-10 logarithm of x for x> 0
max(x,y,z...): largest of its arguments: the value closest to positive infinity
min(x,y,z...):  smallest of its arguments: the value closest to negative infinity
modf(X): fractional and integer parts of x in a two-item tuple. Both parts have the same sign as x. The integer part is returned as a float.
pow(x,y): equivalent to x**y
round(x[,n]): x rounded to n digits from the decimal point. Python rounds away from zero as a tie-breaker: round(0.5) is 1.0 and round(-0.5) is -1.0.
sqrt(x): square root of x for x > 0


Random Number Functions:
used for games, simulations, testing, security, and privacy applications
choice(seq): A random item from a list, tuple, or string.
randrange([start,]stop[,step]): A randomly selected element from range(start, stop, step)
random(): A random float r, such that 0 is less than or equal to r and r is less than 1
seed([x]): Sets the integer starting value used in generating random numbers. Call this function before calling any other random module function. Returns None.
shuffle(lst):
Randomizes the items of a list in place. Returns None.
uniform(x,y):
A random float r, such that x is less than or equal to r and r is less than y


Trigonometric Functions:
acos(x)
Return the arc cosine of x, in radians.
asin(x)
Return the arc sine of x, in radians.
atan(x)
Return the arc tangent of x, in radians.
atan2(y, x)
Return atan(y / x), in radians.
cos(x)
Return the cosine of x radians.
hypot(x, y)
Return the Euclidean norm, sqrt(x*x + y*y).
sin(x)
Return the sine of x radians.
tan(x)
Return the tangent of x radians.
degrees(x)
Converts angle x from radians to degrees.
radians(x)
Converts angle x from degrees to radians.

Mathematical Constants:
pi: mathematical constant pi
e: mathematical constant e


Python Strings:
Strings are amongst the most popular types in Python. We can create them simply by enclosing characters in quotes. Python treats single quotes the same as double quotes. Creating strings is as simple as assigning a value to a variable.

var1 = 'Hello World!'
var2 = "Python Programming"

Accessing Values in Strings:
Python does not support a character type; these are treated as strings of length one, thus also considered a substring.

To access substrings, use the square brackets for slicing along with the index or indices to obtain your substring. 

#!/usr/bin/python

var1 = 'Hello World!'
var2 = "Python Programming"

print "var1[0]: ", var1[0]
print "var2[1:5]: ", var2[1:5]

var1[0]:  H
var2[1:5]:  ytho

Updating Strings
You can "update" an existing string by (re)assigning a variable to another string.
The new value can be related to its previous value or to a completely different string altogether. 

#!/usr/bin/python

var1 = 'Hello World!'
print "Updated String :- ", var1[:6] + 'Python'

Escape Characters
Following table is a list of escape or non-printable characters that can be represented with backslash notation.
\a, \b, \cx, \C-x, \e, \f, \M-\C-x, \n, \nnn, \r, \s, \t, \v, \x, \xnn

String special Operators:
a holds 'Hello' and variable b holds 'Python'
+ concatenation a + b will give HelloPython
* repetition- Creates new strings, concatenating multiple copies of the same string  a*2 will give -HelloHello
[] Slice - Gives the character from the given index: a[1] will give e
[ : ] Range Slice - Gives the characters from the given range: a[1:4] will give ell
in: Membership - Returns true if a character exists in the given string, H in a will give 1
not in:	Membership - Returns true if a character does not exist in the given string, M not in a will give 1
r/R	Raw String - Suppresses actual meaning of Escape characters. The syntax for raw strings is exactly the same as for normal strings with the exception of the raw string operator, the letter "r," which precedes the quotation marks. The "r" can be lowercase (r) or uppercase (R) and must be placed immediately preceding the first quote mark.  print r'\n' prints \n and print R'\n'prints \n
%	Format - Performs String formatting


String Formatting Operator
One of Python's coolest features is the string format operator %. This operator is unique to strings and makes up for the pack of having functions from C's printf() family. 
#!/usr/bin/python

print "My name is %s and weight is %d kg!" % ('Zara', 21)
result −
My name is Zara and weight is 21 kg!


%c: character
%s: string conversion via str() prior to formatting
%i: signed decimal integer
%d: signed decimal integer
%u: unsigned decimal integer
%o: octal integer
%x: hexadecimal integer(lowercase letters)
%X: hexadecimal integer(Upper case letters)
%e: exponential notation(with lowercase 'e')
%E: exponential notation(with UPPERcase 'E')
%f: floating point real number
%g: the shorter of %f and %e
%G: the shorter of %f and %E

*	argument specifies width or precision
-	left justification
+	display the sign
<sp>	leave a blank space before a positive number
#	add the octal leading zero ( '0' ) or hexadecimal leading '0x' or '0X', depending on whether 'x' or 'X' were used.
0	pad from left with zeros (instead of spaces)
%	'%%' leaves you with a single literal '%'
(var)	mapping variable (dictionary arguments)
m.n.	m is the minimum total width and n is the number of digits to display after the decimal point (if appl.)


Triple Quotes:
allowing strings to span multiple lines, including verbatim NEWLINEs, TABs, and any other special characters.

The syntax for triple quotes consists of three consecutive single or double quotes


#!/usr/bin/python

para_str = """this is a long string that is made up of
several lines and non-printable characters such as
TAB ( \t ) and they will show up that way when displayed.
NEWLINEs within the string, whether explicitly given like
this within the brackets [ \n ], or just a NEWLINE within
the variable assignment will also show up.
"""
print para_str

When the above code is executed, it produces the following result. Note how every single special character has been converted to its printed form, right down to the last NEWLINE at the end of the string between the "up." and closing triple quotes. Also note that NEWLINEs occur either with an explicit carriage return at the end of a line or its escape code (\n)

Raw strings do not treat the backslash as a special character at all. Every character you put into a raw string stays the way you wrote it −

Live Demo
#!/usr/bin/python

print 'C:\\nowhere'

When the above code is executed, it produces the following result −

C:\nowhere
Now let's make use of raw string. We would put expression in r'expression' as follows −

Live Demo
#!/usr/bin/python

print r'C:\\nowhere'
When the above code is executed, it produces the following result −

C:\\nowhere

Unicode String
Normal strings in Python are stored internally as 8-bit ASCII, while Unicode strings are stored as 16-bit Unicode. This allows for a more varied set of characters, including special characters from most languages in the world.

#!/usr/bin/python

print u'Hello, world!'

Built-in String Methods:
capitalize()
str = "this is string example....wow!!!"
str.capitalize()

center(width, fillchar):
Returns a space-padded string with the original string centered to a total of width columns.
str.center(width[, fillchar])
#!/usr/bin/python
str = "this is string example....wow!!!"
print "str.center(40, 'a') : ", str.center(40, 'a')

https://www.tutorialspoint.com/python/python_strings.htm























```

