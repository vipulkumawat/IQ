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
Python string method center() returns centered in a string of length width. Padding is done using the specified fillchar.
Parameters
width − This is the total width of the string.
fillchar − This is the filler character.

str = "this is string example....wow!!!"
print "str.center(40, 'a') : ", str.center(40, 'a')
result: str.center(40, 'a') :  aaaathis is string example....wow!!!aaaa

count(str, beg= 0,end=len(string)):
Counts how many times str occurs in string or in a substring of string if starting index beg and ending index end are given.
str.count(sub, start= 0,end=len(string))
Parameters
sub − This is the substring to be searched.
start − Search starts from this index. First character starts from 0 index. By default search starts from 0 index.
end − Search ends from this index. First character starts from 0 index. By default search ends at the last index.

str = "this is string example....wow!!!";

sub = "i";
print "str.count(sub, 4, 40) : ", str.count(sub, 4, 40)
sub = "wow";
print "str.count(sub) : ", str.count(sub)

str.count(sub, 4, 40) :  2
str.count(sub) :  1


Str.decode(encoding='UTF-8',errors='strict'):
string method decode() decodes the string using the codec registered for encoding.
Decodes the string using the codec registered for encoding. encoding defaults to the default string encoding.


Parameters
encoding − This is the encodings to be used. For a list of all encoding schemes please visit: Standard Encodings.
https://docs.python.org/3/library/codecs.html#standard-encodings

errors − This may be given to set a different error handling scheme. The default for errors is 'strict', meaning that encoding errors raise a UnicodeError. Other possible values are 'ignore', 'replace', 'xmlcharrefreplace', 'backslashreplace' and any other name registered via codecs.register_error().
ex: Str = "this is string example....wow!!!";
Str = Str.encode('base64','strict');

print "Encoded String: " + Str
print "Decoded String: " + Str.decode('base64','strict')


encode(encoding='UTF-8',errors='strict')
Returns encoded string version of string; on error, default is to raise a ValueError unless errors is given with 'ignore' or 'replace'

method encode() returns an encoded version of the string. Default encoding is the current default string encoding. The errors may be given to set a different error handling scheme.


Parameters
encoding − This is the encodings to be used. For a list of all encoding schemes please visit: Standard Encodings.

errors − This may be given to set a different error handling scheme. The default for errors is 'strict', meaning that encoding errors raise a UnicodeError. Other possible values are 'ignore', 'replace', 'xmlcharrefreplace', 'backslashreplace' and any other name registered via codecs.register_error().

endswith(suffix, beg=0, end=len(string)):
Determines if string or a substring of string (if starting index beg and ending index end are given) ends with suffix; returns true if so and false otherwise.
returns True if the string ends with the specified suffix, otherwise return False optionally restricting the matching with the given indices start and end.

str.endswith(suffix[, start[, end]])
Parameters
suffix − This could be a string or could also be a tuple of suffixes to look for.
start − The slice begins from here.
end − The slice ends here.

Return Value
TRUE if the string ends with the specified suffix, otherwise FALSE.

str = "this is string example....wow!!!";

suffix = "wow!!!";
print str.endswith(suffix)
print str.endswith(suffix,20)

suffix = "is";
print str.endswith(suffix, 2, 4)
print str.endswith(suffix, 2, 6)



expandtabs(tabsize=8)
Expands tabs in string to multiple spaces; defaults to 8 spaces per tab if tabsize not provided.
returns a copy of the string in which tab characters ie. '\t' are expanded using spaces, optionally using the given tabsize (default 8)

Parameters
tabsize − This specifies the number of characters to be replaced for a tab character '\t'.

Return Value

This method returns a copy of the string in which tab characters i.e., '\t' have been expanded using spaces.


str = "this is\tstring example....wow!!!";

print "Original string: " + str
print "Defualt exapanded tab: " +  str.expandtabs()
print "Double exapanded tab: " +  str.expandtabs(16)


find(str, beg=0 end=len(string)):
Determine if str occurs in string or in a substring of string if starting index beg and ending index end are given returns index if found and -1 otherwise
determines if string str occurs in string, or in a substring of string if starting index beg and ending index end are given.

Syntax
str.find(str, beg=0, end=len(string))
Parameters
str − This specifies the string to be searched.

beg − This is the starting index, by default its 0.

end − This is the ending index, by default its equal to the length of the string.

Return Value
Index if found and -1 otherwise.

str1 = "this is string example....wow!!!";
str2 = "exam";

print str1.find(str2)
print str1.find(str2, 10)
print str1.find(str2, 40)


index(str, beg=0, end=len(string)):
Same as find(), but raises an exception if str not found
method index() determines if string str occurs in string or in a substring of string if starting index beg and ending index end are given. This method is same as find(), but raises an exception if sub is not found.
str.index(str, beg = 0 end = len(string))
Parameters
str − This specifies the string to be searched.
beg − This is the starting index, by default its 0.
end − This is the ending index, by default its equal to the length of the string.

Return Value
Index if found otherwise raises an exception if str is not found
str1 = "this is string example....wow!!!";
str2 = "exam";

print str1.index(str2)
print str1.index(str2, 10)
print str1.index(str2, 40)


isalnum():
Returns true if string has at least 1 character and all characters are alphanumeric and false otherwise.
method isalnum() checks whether the string consists of alphanumeric characters
returns true if all characters in the string are alphanumeric and there is at least one character, false otherwise.

str = "this2009";  # No space in this string
print str.isalnum()

str = "this is string example....wow!!!";
print str.isalnum()
When we run above program, it produces following result −

True
False


isalpha():
Returns true if string has at least 1 character and all characters are alphabetic and false otherwise.
checks whether the string consists of alphabetic characters only
returns true if all characters in the string are alphabetic and there is at least one character, false otherwise.
str = "this";  # No space & digit in this string
print str.isalpha()

str = "this is string example....wow!!!";
print str.isalpha()

isdigit():
Returns true if string contains only digits and false otherwise.
checks whether the string consists of digits only.
method returns true if all characters in the string are digits and there is at least one character, false otherwise.

str = "123456";  # Only digit in this string
print str.isdigit()

str = "this is string example....wow!!!";
print str.isdigit()

islower():
Returns true if string has at least 1 cased character and all cased characters are in lowercase and false otherwise.
eturns true if all cased characters in the string are lowercase and there is at least one cased character, false otherwise.

str = "THIS is string example....wow!!!"; 
print str.islower()

str = "this is string example....wow!!!";
print str.islower()

isnumeric():
Returns true if a unicode string contains only numeric characters and false otherwise.
checks whether the string consists of only numeric characters. This method is present only on unicode objects.

Note − To define a string as Unicode, one simply prefixes a 'u' to the opening quotation mark of the assignment. 
str.isnumeric()
This method returns true if all characters in the string are numeric, false otherwise.
str = u"this2009";  
print str.isnumeric()

str = u"23443434";
print str.isnumeric()

isspace():
method isspace() checks whether the string consists of whitespace.
Returns true if string contains only whitespace characters and false otherwise.
method returns true if there are only whitespace characters in the string and there is at least one character, false otherwise
str = "       "; 
print str.isspace()

str = "This is string example....wow!!!";
print str.isspace()


istitle():
Returns true if string is properly "titlecased" and false otherwise.
checks whether all the case-based characters in the string following non-casebased letters are uppercase and all other case-based characters are lowercase.
 returns true if the string is a titlecased string and there is at least one character, for example uppercase characters may only follow uncased characters and lowercase characters only cased ones.It returns false otherwise

str = "This Is String Example...Wow!!!";
print str.istitle()

str = "This is string example....wow!!!";
print str.istitle()


isupper():
Returns true if string has at least one cased character and all cased characters are in uppercase and false otherwise
checks whether all the case-based characters (letters) of the string are uppercase.

str.isupper()
returns true if all cased characters in the string are uppercase and there is at least one cased character, false otherwise.

str = "THIS IS STRING EXAMPLE....WOW!!!"; 
print str.isupper()

str = "THIS is string example....wow!!!";
print str.isupper()

join(seq):
Merges (concatenates) the string representations of elements in sequence seq into a string, with separator string.
method join() returns a string in which the string elements of sequence have been joined by str separator.
str.join(sequence)

Parameters
sequence − This is a sequence of the elements to be joined.

Return Value
This method returns a string, which is the concatenation of the strings in the sequence seq. The separator between elements is the string providing this method.

s = "-";
seq = ("a", "b", "c"); # This is sequence of strings.
print s.join( seq )

len(string):
Returns the length of the string
len() returns the length of the string.

#!/usr/bin/python

str = "this is string example....wow!!!";
print "Length of the string: ", len(str)

ljust(width[, fillchar]):
returns the string left justified in a string of length width. Padding is done using the specified fillchar (default is a space). The original string is returned if width is less than len(s).

str.ljust(width[, fillchar])
Parameters
width − This is string length in total after padding.

fillchar − This is filler character, default is a space.

Return Value
This method returns the string left justified in a string of length width. Padding is done using the specified fillchar (default is a space). The original string is returned if width is less than len(s)


str = "this is string example....wow!!!";
print str.ljust(50, '0')


lower():
Converts all uppercase letters in string to lowercase.
returns a copy of the string in which all case-based characters have been lowercased.
Return Value
This method returns a copy of the string in which all case-based characters have been lowercased.

str = "THIS IS STRING EXAMPLE....WOW!!!";
print str.lower()

lstrip():
Removes all leading whitespace in string.
returns a copy of the string in which all chars have been stripped from the beginning of the string (default whitespace characters).
str.lstrip([chars])
Parameters
chars − You can supply what chars have to be trimmed.
This method returns a copy of the string in which all chars have been stripped from the beginning of the string (default whitespace characters).

str = "     this is string example....wow!!!     ";
print str.lstrip()
str = "88888888this is string example....wow!!!8888888";
print str.lstrip('8')



maketrans():
Returns a translation table to be used in translate function.
 returns a translation table that maps each character in the intabstring into the character at the same position in the outtab string. Then this table is passed to the translate() function.
str.maketrans(intab, outtab)
Parameters
intab − This is the string having actual characters.
outtab − This is the string having corresponding mapping character.

returns a translate table to be used translate() function

from string import maketrans   # Required to call maketrans function.

intab = "aeiou"
outtab = "12345"
trantab = maketrans(intab, outtab)

str = "this is string example....wow!!!"
print str.translate(trantab)


max(str):
Returns the max alphabetical character from the string str.
method max() returns the max alphabetical character from the string str.
Parameters
str − This is the string from which max alphabetical character needs to be returned.

str = "this is really a string example....wow!!!";
print "Max character: " + max(str)

str = "this is a string example....wow!!!";
print "Max character: " + max(str)


min(str):
Returns the min alphabetical character from the string str

str = "this-is-real-string-example....wow!!!";
print "Min character: " + min(str)

str = "this-is-a-string-example....wow!!!";
print "Min character: " + min(str)

replace(old, new [, max]):
Replaces all occurrences of old in string with new or at most max occurrences if max given.
returns a copy of the string in which the occurrences of old have been replaced with new, optionally restricting the number of replacements to max.

Parameters
old − This is old substring to be replaced.
new − This is new substring, which would replace old substring.
max − If this optional argument max is given, only the first count occurrences are replaced

Return Value
This method returns a copy of the string with all occurrences of substring old replaced by new. If the optional argument max is given, only the first count occurrences are replaced.


str = "this is string example....wow!!! this is really string";
print str.replace("is", "was");
print str.replace("is", "was", 3);


rfind(str, beg=0,end=len(string)):
Same as find(), but search backwards in string.
rfind() returns the last index where the substring str is found, or -1 if no such index exists, optionally restricting the search to string[beg:end].
obj.rfind(str, beg=0 end=len(string))
Parameters
str − This specifies the string to be searched.
beg − This is the starting index, by default its 0.
end − This is the ending index, by default its equal to the length of the string.

str1 = "this is really a string example....wow!!!";
str2 = "is";

print str1.rfind(str2)
print str1.rfind(str2, 0, 10)
print str1.rfind(str2, 10, 0)

print str1.find(str2)
print str1.find(str2, 0, 10)
print str1.find(str2, 10, 0)


rindex( str, beg=0, end=len(string)):
Same as index(), but search backwards in string.
Python string method rindex() returns the last index where the substring str is found, or raises an exception if no such index exists, optionally restricting the search to string[beg:end].

str.rindex(str, beg=0 end=len(string))
Parameters
str − This specifies the string to be searched.
beg − This is the starting index, by default its 0
len − This is ending index, by default its equal to the length of the string.

Return Value
This method returns last index if found otherwise raises an exception if str is not found.

str1 = "this is string example....wow!!!";
str2 = "is";

print str1.rindex(str2)
print str1.index(str2)


rjust(width,[, fillchar]):
Returns a space-padded string with the original string right-justified to a total of width columns.
rjust() returns the string right justified in a string of length width. Padding is done using the specified fillchar (default is a space). The original string is returned if width is less than len(s).
Parameters
width − This is the string length in total after padding.
fillchar − This is the filler character, default is a space.
returns the string right justified in a string of length width. Padding is done using the specified fillchar (default is a space). The original string is returned if width is less than len(s).

str = "this is string example....wow!!!";
print str.rjust(50, '0')

rstrip():
Removes all trailing whitespace of string.

rstrip() returns a copy of the string in which all chars have been stripped from the end of the string (default whitespace characters).
str.rstrip([chars])
Parameters
chars − You can supply what chars have to be trimmed.

Return Value
This method returns a copy of the string in which all chars have been stripped from the end of the string (default whitespace characters).

str = "     this is string example....wow!!!     ";
print str.rstrip()
str = "88888888this is string example....wow!!!8888888";
print str.rstrip('8')

split(str="", num=string.count(str)):
Splits string according to delimiter str (space if not provided) and returns list of substrings; split into at most num substrings if given.
method split() returns a list of all the words in the string, using str as the separator (splits on all whitespace if left unspecified), optionally limiting the number of splits to num.
str.split(str="", num=string.count(str))
Parameters:
str − This is any delimeter, by default it is space.
num − this is number of lines minus one

Return Value
This method returns a list of lines.

str = "Line1-abcdef \nLine2-abc \nLine4-abcd";
print str.split( )
print str.split(' ', 1 )


splitlines( num=string.count('\n')):
Splits string at all (or num) NEWLINEs and returns a list of each line with NEWLINEs removed.
method splitlines() returns a list with all the lines in string, optionally including the line breaks (if num is supplied and is true)
Parameters
Keepends − This is an optional parameter, if its value as true, line breaks need are also included in the output.
str = "Line1-a b c d e f\nLine2- a b c\n\nLine4- a b c d";
print str.splitlines( )
print str.splitlines( 0 )
print str.splitlines( 3 )
print str.splitlines( 4 )
print str.splitlines( 5 )



str = "Line1-a b c d e f\nLine2- a b c\n\nLine4- a b c d";
print str.splitlines(True)
print str.splitlines( 0 )
print str.splitlines( 3 )
print str.splitlines( 4 )
print str.splitlines( 5 )


startswith(str, beg=0,end=len(string)):
Determines if string or a substring of string (if starting index beg and ending index end are given) starts with substring str; returns true if so and false otherwise.
method startswith() checks whether string starts with str, optionally restricting the matching with the given indices start and end.
Parameters
str − This is the string to be checked.

beg − This is the optional parameter to set start index of the matching boundary.

end − This is the optional parameter to end start index of the matching boundary.

Return Value
This method returns true if found matching string otherwise false.

str = "this is string example....wow!!!";
print str.startswith( 'this' )
print str.startswith( 'is', 2, 4 )
print str.startswith( 'this', 2, 4 )

strip([chars]):
Performs both lstrip() and rstrip() on string.
method strip() returns a copy of the string in which all chars have been stripped from the beginning and the end of the string (default whitespace characters).

Parameters
chars − The characters to be removed from beginning or end of the string.


Return Value
This method returns a copy of the string in which all chars have been stripped from the beginning and the end of the string.

str = "0000000this is string example....wow!!!0000000";
print str.strip( '0' )


swapcase():
Inverts case for all letters in string.
method swapcase() returns a copy of the string in which all the case-based characters have had their case swapped.
str.swapcase();
returns a copy of the string in which all the case-based characters have had their case swapped.

str = "this is string example....wow!!!";
print str.swapcase()

str = "THIS IS STRING EXAMPLE....WOW!!!";
print str.swapcase()

title():
Returns "titlecased" version of string, that is, all words begin with uppercase and the rest are lowercase.
returns a copy of the string in which first characters of all the words are capitalized.

str = "this is string example....wow!!!";
print str.title()

translate(table, deletechars=""):
Translates string according to translation table str(256 chars), removing those in the del string.
returns a copy of the string in which all characters have been translated using table (constructed with the maketrans() function in the string module), optionally deleting all characters found in the string deletechars.
Parameters
table − You can use the maketrans() helper function in the string module to create a translation table.

deletechars − The list of characters to be removed from the source string.

returns a translated copy of the string.

from string import maketrans   # Required to call maketrans function.

intab = "aeiou"
outtab = "12345"
trantab = maketrans(intab, outtab)

str = "this is string example....wow!!!";
print str.translate(trantab)



from string import maketrans   # Required to call maketrans function.

intab = "aeiou"
outtab = "12345"
trantab = maketrans(intab, outtab)

str = "this is string example....wow!!!";
print str.translate(trantab, 'xm')


upper():
Converts lowercase letters in string to uppercase.
returns a copy of the string in which all case-based characters have been uppercased.

str = "this is string example....wow!!!";
print "str.capitalize() : ", str.upper()

zfill (width):
Returns original string leftpadded with zeros to a total of width characters; intended for numbers, zfill() retains any sign given (less one zero).

 method zfill() pads string on the left with zeros to fill width.

str.zfill(width)

width − This is final width of the string. This is the width which we would get after filling zeros.

str = "this is string example....wow!!!";
print str.zfill(40)
print str.zfill(50)

isdecimal():
Returns true if a unicode string contains only decimal characters and false otherwise.

method isdecimal() checks whether the string consists of only decimal characters. This method are present only on unicode objects.

Note − To define a string as Unicode, one simply prefixes a 'u' to the opening quotation mark of the assignment. 



str = u"this2009";  
print str.isdecimal();

str = u"23443434";
print str.isdecimal();




Python - Lists:
 basic data structure in Python is the sequence. Each element of a sequence is assigned a number - its position or index. The first index is zero, the second index is one, and so forth.

Python has six built-in types of sequences, but the most common ones are lists and tuples, which we would see in this tutorial.

There are certain things you can do with all sequence types. These operations include indexing, slicing, adding, multiplying, and checking for membership. In addition, Python has built-in functions for finding the length of a sequence and for finding its largest and smallest elements.




list is a most versatile datatype available in Python which can be written as a list of comma-separated values (items) between square brackets. Important thing about a list is that items in a list need not be of the same type.

Creating a list is as simple as putting different comma-separated values between square brackets. 

list1 = ['physics', 'chemistry', 1997, 2000];
list2 = [1, 2, 3, 4, 5 ];
list3 = ["a", "b", "c", "d"]


Similar to string indices, list indices start at 0, and lists can be sliced, concatenated and so on.


Accessing Values in Lists
To access values in lists, use the square brackets for slicing along with the index or indices to obtain value available at that index. 

list1 = ['physics', 'chemistry', 1997, 2000];
list2 = [1, 2, 3, 4, 5, 6, 7 ];
print "list1[0]: ", list1[0]
print "list2[1:5]: ", list2[1:5]



Updating Lists
You can update single or multiple elements of lists by giving the slice on the left-hand side of the assignment operator, and you can add to elements in a list with the append() method. 

list = ['physics', 'chemistry', 1997, 2000];
print "Value available at index 2 : "
print list[2]
list[2] = 2001;
print "New value available at index 2 : "
print list[2]


Delete List Elements
To remove a list element, you can use either the del statement if you know exactly which element(s) you are deleting or the remove() method if you do not know.


list1 = ['physics', 'chemistry', 1997, 2000];
print list1
del list1[2];
print "After deleting value at index 2 : "
print list1


Basic List Operations
Lists respond to the + and * operators much like strings; they mean concatenation and repetition here too, except that the result is a new list, not a string.

lists respond to all of the general sequence operations we used on strings in the prior chapter.

len([1, 2, 3]): length
[1, 2, 3] + [4, 5, 6]: concatination
['Hi!'] * 4: repetition
3 in [1, 2, 3]: membership
for x in [1, 2, 3]: print x, : Iteration

Indexing, Slicing, and Matrixes:
 lists are sequences, indexing and slicing work the same way for lists as they do for strings

L = ['spam', 'Spam', 'SPAM!']
L[2]	SPAM!	Offsets start at zero
L[-2]	Spam	Negative: count from the right
L[1:]	['Spam', 'SPAM!']	Slicing fetches sections


Built-in List Functions & Methods
Python includes the following list functions −
cmp(list1, list2):
Compares elements of both lists.
method cmp() compares elements of two lists

Return Value
If elements are of the same type, perform the compare and return the result. If elements are different types, check to see if they are numbers.

If numbers, perform numeric coercion if necessary and compare.
If either element is a number, then the other element is "larger" (numbers are "smallest").
Otherwise, types are sorted alphabetically by name.
If we reached the end of one of the lists, the longer list is "larger." If we exhaust both lists and share the same data, the result is a tie, meaning that 0 is returned.


list1, list2 = [123, 'xyz'], [456, 'abc']
print cmp(list1, list2)
print cmp(list2, list1)
list3 = list2 + [786];
print cmp(list2, list3)


len(list):
Gives the total length of the list.
returns the number of elements in the list.
list1, list2 = [123, 'xyz', 'zara'], [456, 'abc']
print "First list length : ", len(list1)
print "Second list length : ", len(list2)

max(list):
Returns item from the list with max value.
method max returns the elements from the list with maximum value.
list1, list2 = [123, 'xyz', 'zara', 'abc'], [456, 700, 200]
print "Max value element : ", max(list1)
print "Max value element : ", max(list2)


min(list):
Returns item from the list with min value.

returns the elements from the list with minimum value.
list1, list2 = [123, 'xyz', 'zara', 'abc'], [456, 700, 200]
print "min value element : ", min(list1)
print "min value element : ", min(list2)


list(seq):
Converts a tuple into list.
method list() takes sequence types and converts them to lists. This is used to convert a given tuple into list.

Note − Tuple are very similar to lists with only difference that element values of a tuple can not be changed and tuple elements are put between parentheses instead of square bracket.

aTuple = (123, 'xyz', 'zara', 'abc');
aList = list(aTuple)
print "List elements : ", aList


list.append(obj):
Appends object obj to list
list method append() appends a passed obj into the existing list.

This method does not return any value but updates existing list.

aList = [123, 'xyz', 'zara', 'abc'];
aList.append( 2009 );
print "Updated List : ", aList


list.count(obj):
Returns count of how many times obj occurs in list
method count() returns count of how many times obj occurs in list.
 returns count of how many times obj occurs in list.

aList = [123, 'xyz', 'zara', 'abc', 123];
print "Count for 123 : ", aList.count(123)
print "Count for zara : ", aList.count('zara')


list.extend(seq):
Appends the contents of seq to list
method extend() appends the contents of seq to list.
This method does not return any value but add the content to existing list.

aList = [123, 'xyz', 'zara', 'abc', 123];
bList = [2009, 'manni'];
aList.extend(bList)
print "Extended List : ", aList 

list.index(obj):
Returns the lowest index in list that obj appears
This method returns index of the found object otherwise raise an exception indicating that value does not find.

aList = [123, 'xyz', 'zara', 'abc'];
print "Index for xyz : ", aList.index( 'xyz' ) 
print "Index for zara : ", aList.index( 'zara' )


list.insert(index, obj):
Inserts object obj into list at offset index
method insert() inserts object obj into list at offset index.

This method does not return any value but it inserts the given element at the given index.

aList = [123, 'xyz', 'zara', 'abc']
aList.insert( 3, 2009)
print "Final List : ", aList


list.pop(obj=list[-1])
Removes and returns last object or obj from list

removes and returns last object or obj from the list.

This method returns the removed object from the list.

aList = [123, 'xyz', 'zara', 'abc'];
print "A List : ", aList.pop()
print "B List : ", aList.pop(2)

list.remove(obj):
Removes object obj from list
method remove() searches for the given element in the list and removes the first matching element.
does not return any value but removes the given object from the list.

aList = [123, 'xyz', 'zara', 'abc', 'xyz'];
aList.remove('xyz');
print "List : ", aList
aList.remove('abc');
print "List : ", aList


list.reverse():
Reverses objects of list in place
method reverse() reverses objects of list in place.

aList = [123, 'xyz', 'zara', 'abc', 'xyz'];
aList.reverse();
print "List : ", aList

list.sort([func]):
Sorts objects of list, use compare func if given
does not return any value but it changes from the original list.

aList = [123, 'xyz', 'zara', 'abc', 'xyz'];
aList.sort();
print "List : ", aList

Tuples:
A tuple is a collection of objects which ordered and immutable. Tuples are sequences, just like lists. The differences between tuples and lists are, the tuples cannot be changed unlike lists and tuples use parentheses, whereas lists use square brackets.

Creating a tuple is as simple as putting different comma-separated values. Optionally you can put these comma-separated values between parentheses also. For example −

tup1 = ('physics', 'chemistry', 1997, 2000);
tup2 = (1, 2, 3, 4, 5 );
tup3 = "a", "b", "c", "d";
The empty tuple is written as two parentheses containing nothing −

tup1 = ();
To write a tuple containing a single value you have to include a comma, even though there is only one value −

tup1 = (50,);
Like string indices, tuple indices start at 0, and they can be sliced, concatenated, and so on.

Accessing Values in Tuples
To access values in tuple, use the square brackets for slicing along with the index or indices to obtain value available at that index. For example −

 Live Demo
#!/usr/bin/python

tup1 = ('physics', 'chemistry', 1997, 2000);
tup2 = (1, 2, 3, 4, 5, 6, 7 );
print "tup1[0]: ", tup1[0];
print "tup2[1:5]: ", tup2[1:5];


Updating Tuples
Tuples are immutable which means you cannot update or change the values of tuple elements. You are able to take portions of existing tuples to create new tuples as the following example demonstrates −

 Live Demo
#!/usr/bin/python

tup1 = (12, 34.56);
tup2 = ('abc', 'xyz');

# Following action is not valid for tuples
# tup1[0] = 100;

# So let's create a new tuple as follows
tup3 = tup1 + tup2;
print tup3;



Delete Tuple Elements
Removing individual tuple elements is not possible. There is, of course, nothing wrong with putting together another tuple with the undesired elements discarded.

To explicitly remove an entire tuple, just use the del statement. For example −

 Live Demo
#!/usr/bin/python

tup = ('physics', 'chemistry', 1997, 2000);
print tup;
del tup;
print "After deleting tup : ";
print tup;


Note an exception raised, this is because after del tup tuple does not exist any more −


Basic Tuples Operations:
Tuples respond to the + and * operators much like strings; they mean concatenation and repetition here too, except that the result is a new tuple, not a string.

In fact, tuples respond to all of the general sequence operations we used on strings 

len((1,2,3))
(1,2,3)+(4,5,6)
('Hi!',)*4
3 in (1,2,3)
for x in(1,2,3): print x
Indexing, Slicing, and Matrixes:
Because tuples are sequences, indexing and slicing work the same way for tuples as they do for strings.
L = ('spam', 'Spam', 'SPAM!')
L[2]
L[-2]
L[1:]


No Enclosing Delimiters
Any set of multiple objects, comma-separated, written without identifying symbols, i.e., brackets for lists, parentheses for tuples, etc., default to tuples, as indicated in these short examples
#!/usr/bin/python

print 'abc', -4.24e93, 18+6.6j, 'xyz';
x, y = 1, 2;
print "Value of x , y : ", x,y;


Built-in Tuple Functions:
cmp(tuple1, tuple2)
Compares elements of both tuples
If elements are of the same type, perform the compare and return the result. If elements are different types, check to see if they are numbers.

If numbers, perform numeric coercion if necessary and compare.

If either element is a number, then the other element is "larger" (numbers are "smallest").

Otherwise, types are sorted alphabetically by name.

If we reached the end of one of the tuples, the longer tuple is "larger." If we exhaust both tuples and share the same data, the result is a tie, meaning that 0 is returned.

tuple1, tuple2 = (123, 'xyz'), (456, 'abc')
print cmp(tuple1, tuple2)
print cmp(tuple2, tuple1)
tuple3 = tuple2 + (786,);
print cmp(tuple2, tuple3)


len(tuple)
Gives the total length of the tuple.
tuple1, tuple2 = (123, 'xyz', 'zara'), (456, 'abc')
print "First tuple length : ", len(tuple1)
print "Second tuple length : ", len(tuple2)


max(tuple)
Returns item from the tuple with max value.
tuple1, tuple2 = (123, 'xyz', 'zara', 'abc'), (456, 700, 200)
print "Max value element : ", max(tuple1)
print "Max value element : ", max(tuple2)


min(tuple)
Returns item from the tuple with min value.

tuple1, tuple2 = (123, 'xyz', 'zara', 'abc'), (456, 700, 200)
print "min value element : ", min(tuple1)
print "min value element : ", min(tuple2)


tuple(seq)
Converts a list into tuple.

aList = [123, 'xyz', 'zara', 'abc']
aTuple = tuple(aList)
print "Tuple elements : ", aTuple


Dictionary:
Each key is separated from its value by a colon (:), the items are separated by commas, and the whole thing is enclosed in curly braces. An empty dictionary without any items is written with just two curly braces, like this: {}.

Keys are unique within a dictionary while values may not be. The values of a dictionary can be of any type, but the keys must be of an immutable data type such as strings, numbers, or tuples.

dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
print "dict['Name']: ", dict['Name']
print "dict['Age']: ", dict['Age']

If we attempt to access a data item with a key, which is not part of the dictionary, we get an error as follows −

 Live Demo
#!/usr/bin/python

dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
print "dict['Alice']: ", dict['Alice']
When the above code is executed, it produces the following result −

dict['Alice']:
Traceback (most recent call last):
File "test.py", line 4, in <module>
print "dict['Alice']: ", dict['Alice'];
KeyError: 'Alice'


Updating Dictionary
You can update a dictionary by adding a new entry or a key-value pair, modifying an existing entry, or deleting an existing entry as shown below in the simple example −

#!/usr/bin/python

dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
dict['Age'] = 8; # update existing entry
dict['School'] = "DPS School"; # Add new entry

print "dict['Age']: ", dict['Age']
print "dict['School']: ", dict['School']


Delete Dictionary Elements
You can either remove individual dictionary elements or clear the entire contents of a dictionary. You can also delete entire dictionary in a single operation.

To explicitly remove an entire dictionary, just use the del statement. Following is a simple example −

#!/usr/bin/python

dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
del dict['Name']; # remove entry with key 'Name'
dict.clear();     # remove all entries in dict
del dict ;        # delete entire dictionary

print "dict['Age']: ", dict['Age']
print "dict['School']: ", dict['School']

Note that an exception is raised because after del dict dictionary does not exist any more

Properties of Dictionary Keys
Dictionary values have no restrictions. They can be any arbitrary Python object, either standard objects or user-defined objects. However, same is not true for the keys.

There are two important points to remember about dictionary keys −

(a) More than one entry per key not allowed. Which means no duplicate key is allowed. When duplicate keys encountered during assignment, the last assignment wins. 

dict = {'Name': 'Zara', 'Age': 7, 'Name': 'Manni'}
print "dict['Name']: ", dict['Name']

(b) Keys must be immutable. Which means you can use strings, numbers or tuples as dictionary keys but something like ['key'] is not allowed.

dict = {['Name']: 'Zara', 'Age': 7}
print "dict['Name']: ", dict['Name']
When the above code is executed, it produces the following result −

Traceback (most recent call last):
File "test.py", line 3, in <module>
dict = {['Name']: 'Zara', 'Age': 7};
TypeError: unhashable type: 'list'

Built-in Dictionary Functions & Methods:

cmp(dict1, dict2)
Compares elements of both dict
method cmp() compares two dictionaries based on key and values.
This method returns 0 if both dictionaries are equal, -1 if dict1 < dict2 and 1 if dict1 > dic2.


dict1 = {'Name': 'Zara', 'Age': 7};
dict2 = {'Name': 'Mahnaz', 'Age': 27};
dict3 = {'Name': 'Abid', 'Age': 27};
dict4 = {'Name': 'Zara', 'Age': 7};
print "Return Value : %d" %  cmp (dict1, dict2)
print "Return Value : %d" %  cmp (dict2, dict3)
print "Return Value : %d" %  cmp (dict1, dict4)



len(dict)
Gives the total length of the dictionary. This would be equal to the number of items in the dictionary.
dict = {'Name': 'Zara', 'Age': 7};
print "Length : %d" % len (dict)

str(dict)
Produces a printable string representation of a dictionary
dict = {'Name': 'Zara', 'Age': 7};
print "Equivalent String : %s" % str (dict)

type(variable)
Returns the type of the passed variable. If passed variable is dictionary, then it would return a dictionary type.

dict = {'Name': 'Zara', 'Age': 7};
print "Variable Type : %s" %  type (dict)


Python includes following dictionary methods −


dict.clear()
Removes all elements of dictionary dict
method clear() removes all items from the dictionary.

dict = {'Name': 'Zara', 'Age': 7};
print "Start Len : %d" %  len(dict)
dict.clear()
print "End Len : %d" %  len(dict)


dict.copy()
Returns a shallow copy of dictionary dict
method copy() returns a shallow copy of the dictionary.

dict1 = {'Name': 'Zara', 'Age': 7};
dict2 = dict1.copy()
print "New Dictionary : %s" %  str(dict2)


dict.fromkeys()
Create a new dictionary with keys from seq and values set to value.

method fromkeys() creates a new dictionary with keys from seq and values set to value.

seq = ('name', 'age', 'sex')
dict = dict.fromkeys(seq)
print "New Dictionary : %s" %  str(dict)

dict = dict.fromkeys(seq, 10)
print "New Dictionary : %s" %  str(dict)

dict.get(key, default=None)
For key key, returns value or default if key not in dictionary
Python dictionary method get() returns a value for the given key. If key is not available then returns default value None.
key − This is the Key to be searched in the dictionary.
default − This is the Value to be returned in case key does not exist.

This method return a value for the given key. If key is not available, then returns default value None.


dict = {'Name': 'Zabra', 'Age': 7}
print "Value : %s" %  dict.get('Age')
print "Value : %s" %  dict.get('Education', "Never")

dict.has_key(key)
Returns true if key in dictionary dict, false otherwise
returns true if a given key is available in the dictionary, otherwise it returns a false.

dict = {'Name': 'Zara', 'Age': 7}
print "Value : %s" %  dict.has_key('Age')
print "Value : %s" %  dict.has_key('Sex')

dict.items()
Returns a list of dict's (key, value) tuple pairs
 returns a list of tuple pairs
dict = {'Name': 'Zara', 'Age': 7}
print "Value : %s" %  dict.items()


dict.keys()
Returns list of dictionary dict's keys
returns a list of all the available keys in the dictionary.
dict = {'Name': 'Zara', 'Age': 7}
print "Value : %s" %  dict.keys()


dict.setdefault(key, default=None)
Similar to get(), but will set dict[key]=default if key is not already in dict
method setdefault() is similar to get(), but will set dict[key]=default if key is not already in dict.
key − This is the key to be searched.
default − This is the Value to be returned in case key is not found.

dict = {'Name': 'Zara', 'Age': 7}
print "Value : %s" %  dict.setdefault('Age', None)
print "Value : %s" %  dict.setdefault('Sex', None)


dict.update(dict2)
Adds dictionary dict2's key-values pairs to dict
method update() adds dictionary dict2's key-values pairs in to dict.

dict = {'Name': 'Zara', 'Age': 7}
dict2 = {'Sex': 'female' }

dict.update(dict2)
print "Value : %s" %  dict


dict.values()
Returns list of dictionary dict's values
returns a list of all the values available in a given dictionary.

dict = {'Name': 'Zara', 'Age': 7}
print "Value : %s" %  dict.values()







Date & Time:
A Python program can handle date and time in several ways. Converting between date formats is a common chore for computers. Python's time and calendar modules help track dates and times.


There is a popular time module available in Python which provides functions for working with times, and for converting between representations. The function time.time() returns the current system time in ticks since 00:00:00 hrs January 1, 1970(epoch).
Time intervals are floating-point numbers in units of seconds. 
Date arithmetic is easy to do with ticks. However, dates before the epoch cannot be represented in this form. Dates in the far future also cannot be represented this way - the cutoff point is sometime in 2038 for UNIX and Windows.

Many of Python's time functions handle time as a tuple of 9 numbers,
0	4-digit year	2008
1	Month	1 to 12
2	Day	1 to 31
3	Hour	0 to 23
4	Minute	0 to 59
5	Second	0 to 61 (60 or 61 are leap-seconds)
6	Day of Week	0 to 6 (0 is Monday)
7	Day of year	1 to 366 (Julian day)
8	Daylight savings	-1, 0, 1, -1 means library determines DST


The above tuple is equivalent to struct_time structure. 

Index	Attributes	Values
0	tm_year	2008
1	tm_mon	1 to 12
2	tm_mday	1 to 31
3	tm_hour	0 to 23
4	tm_min	0 to 59
5	tm_sec	0 to 61 (60 or 61 are leap-seconds)
6	tm_wday	0 to 6 (0 is Monday)
7	tm_yday	1 to 366 (Julian day)
8	tm_isdst	-1, 0, 1, -1 means library determines DST


Getting current time
To translate a time instant from a seconds since the epoch floating-point value into a time-tuple, pass the floating-point value to a function (e.g., localtime) that returns a time-tuple with all nine items valid.

#!/usr/bin/python
import time;

localtime = time.localtime(time.time())
print "Local current time :", localtime


Getting formatted time
You can format any time as per your requirement, but simple method to get time in readable format is asctime()

import time;

localtime = time.asctime( time.localtime(time.time()) )
print "Local current time :", localtime


Getting calendar for a month
The calendar module gives a wide range of methods to play with yearly and monthly calendars

import calendar

cal = calendar.month(2008, 1)
print "Here is the calendar:"
print cal

The time Module
There is a popular time module available in Python which provides functions for working with times and for converting between representations.


time.altzone:
method altzone() is the attribute of the time module. This returns the offset of the local DST timezone, in seconds west of UTC, if one is defined. This is negative if the local DST timezone is east of UTC (as in Western Europe, including the UK). Only use this if daylight is nonzero
returns the offset of the local DST timezone, in seconds west of UTC, if one is defined.
import time

print "time.altzone %d " % time.altzone

time.asctime([tupletime]):
Accepts a time-tuple and returns a readable 24-character string such as 'Tue Dec 11 18:07:14 2008'.
import time

t = time.localtime()
print "time.asctime(t): %s " % time.asctime(t)

time.clock( ):
Returns the current CPU time as a floating-point number of seconds. To measure computational costs of different approaches, the value of time.clock is more useful than that of time.time().

import time

def procedure():
   time.sleep(2.5)

# measure process time
t0 = time.clock()
procedure()
print time.clock(), "seconds process time"

# measure wall time
t0 = time.time()
procedure()
print time.time() - t0, "seconds wall time"

time.ctime([secs]):
Like asctime(localtime(secs)) and without arguments is like asctime( )
converts a time expressed in seconds since the epoch to a string representing local time. If secs is not provided or None, the current time as returned by time() is used. This function is equivalent to asctime(localtime(secs)). Locale information is not used by ctime().

import time

print "time.ctime() : %s" % time.ctime()

time.gmtime([secs]):
Accepts an instant expressed in seconds since the epoch and returns a time-tuple t with the UTC time. 
converts a time expressed in seconds since the epoch to a struct_time in UTC in which the dst flag is always zero. If secs is not provided or None, the current time as returned by time() is used.

import time

print "time.gmtime() : %s" % time.gmtime()

time.localtime([secs]):
Accepts an instant expressed in seconds since the epoch and returns a time-tuple t with the local time (t.tm_isdst is 0 or 1, depending on whether DST applies to instant secs by local rules).

method localtime() is similar to gmtime() but it converts number of seconds to local time. If secs is not provided or None, the current time as returned by time() is used. The dst flag is set to 1 when DST applies to the given time.
import time

print "time.localtime() : %s" % time.localtime()

time.mktime(tupletime):
Accepts an instant expressed as a time-tuple in local time and returns a floating-point value with the instant expressed in seconds since the epoch.
 method mktime() is the inverse function of localtime(). Its argument is the struct_time or full 9-tuple and it returns a floating point number, for compatibility with time().

If the input value cannot be represented as a valid time, either OverflowError or ValueError will be raised.

import time

t = (2009, 2, 17, 17, 3, 38, 1, 48, 0)
secs = time.mktime( t )
print "time.mktime(t) : %f" %  secs
print "asctime(localtime(secs)): %s" % time.asctime(time.localtime(secs))


time.sleep(secs):
Suspends the calling thread for secs seconds.
method sleep() suspends execution for the given number of seconds. The argument may be a floating point number to indicate a more precise sleep time.

The actual suspension time may be less than that requested because any caught signal will terminate the sleep() following execution of that signal's catching routine.

import time

print "Start : %s" % time.ctime()
time.sleep( 5 )
print "End : %s" % time.ctime()


time.strftime(fmt[,tupletime]):
Accepts an instant expressed as a time-tuple in local time and returns a string representing the instant as specified by string fmt
converts a tuple or struct_time representing a time as returned by gmtime() or localtime() to a string as specified by the format argument.

If t is not provided, the current time as returned by localtime() is used. format must be a string. An exception ValueError is raised if any field in t is outside of the allowed range.
t − This is the time in number of seconds to be formatted.

format − This is the directive which would be used to format given time. The following directives can be embedded in the format string −
import time

t = (2009, 2, 17, 17, 3, 38, 1, 48, 0)
t = time.mktime(t)
print time.strftime("%b %d %Y %H:%M:%S", time.gmtime(t))

Directive
%a - abbreviated weekday name

%A - full weekday name

%b - abbreviated month name

%B - full month name

%c - preferred date and time representation

%C - century number (the year divided by 100, range 00 to 99)

%d - day of the month (01 to 31)

%D - same as %m/%d/%y

%e - day of the month (1 to 31)

%g - like %G, but without the century

%G - 4-digit year corresponding to the ISO week number (see %V).

%h - same as %b

%H - hour, using a 24-hour clock (00 to 23)

%I - hour, using a 12-hour clock (01 to 12)

%j - day of the year (001 to 366)

%m - month (01 to 12)

%M - minute

%n - newline character

%p - either am or pm according to the given time value

%r - time in a.m. and p.m. notation

%R - time in 24 hour notation

%S - second

%t - tab character

%T - current time, equal to %H:%M:%S

%u - weekday as a number (1 to 7), Monday=1. Warning: In Sun Solaris Sunday=1

%U - week number of the current year, starting with the first Sunday as the first day of the first week

%V - The ISO 8601 week number of the current year (01 to 53), where week 1 is the first week that has at least 4 days in the current year, and with Monday as the first day of the week

%W - week number of the current year, starting with the first Monday as the first day of the first week

%w - day of the week as a decimal, Sunday=0

%x - preferred date representation without the time

%X - preferred time representation without the date

%y - year without a century (range 00 to 99)

%Y - year including the century

%Z or %z - time zone or name or abbreviation

%% - a literal % character

time.strptime(str,fmt='%a %b %d %H:%M:%S %Y'):
Parses str according to format string fmt and returns the instant in time-tuple format
method strptime() parses a string representing a time according to a format. The return value is a struct_time as returned by gmtime() or localtime().

The format parameter uses the same directives as those used by strftime(); it defaults to "%a %b %d %H:%M:%S %Y" which matches the formatting returned by ctime().

If string cannot be parsed according to format, or if it has excess data after parsing, ValueError is raised.

string − This is the time in string format which would be parsed based on the given format.

format − This is the directive which would be used to parse the given string.
import time

struct_time = time.strptime("30 Nov 00", "%d %b %y")
print "returned tuple: %s " % struct_time

	time.time( ):
Returns the current time instant, a floating-point number of seconds since the epoch.
method time() returns the time as a floating point number expressed in seconds since the epoch, in UTC.

Note − Even though the time is always returned as a floating point number, not all systems provide time with a better precision than 1 second. While this function normally returns non-decreasing values, it can return a lower value than a previous call if the system clock has been set back between the two calls.

import time

print "time.time(): %f " %  time.time()
print time.localtime( time.time() )
print time.asctime( time.localtime(time.time()) )

time.tzset():
Resets the time conversion rules used by the library routines. The environment variable TZ specifies how this is done.
method tzset() resets the time conversion rules used by the library routines. The environment variable TZ specifies how this is done.
import time
import os

os.environ['TZ'] = 'EST+05EDT,M4.1.0,M10.5.0'
time.tzset()
print time.strftime('%X %x %Z')

os.environ['TZ'] = 'AEST-10AEDT-11,M10.5.0,M3.5.0'
time.tzset()
print time.strftime('%X %x %Z')

The calendar Module:
By default, calendar takes Monday as the first day of the week and Sunday as the last one. To change this, call calendar.setfirstweekday() function.

Here is a list of functions available with the calendar module −
calendar.calendar(year,w=2,l=1,c=6)

Returns a multiline string with a calendar for year year formatted into three columns separated by c spaces. w is the width in characters of each date; each line has length 21*w+18+2*c. l is the number of lines for each week.

calendar.firstweekday( )

Returns the current setting for the weekday that starts each week. By default, when calendar is first imported, this is 0, meaning Monday.

calendar.isleap(year)

Returns True if year is a leap year; otherwise, False

calendar.leapdays(y1,y2)

Returns the total number of leap days in the years within range(y1,y2).

calendar.month(year,month,w=2,l=1)

Returns a multiline string with a calendar for month month of year year, one line per week plus two header lines. w is the width in characters of each date; each line has length 7*w+6. l is the number of lines for each week.

calendar.monthcalendar(year,month)

Returns a list of lists of ints. Each sublist denotes a week. Days outside month month of year year are set to 0; days within the month are set to their day-of-month, 1 and up.



calendar.monthrange(year,month)

Returns two integers. The first one is the code of the weekday for the first day of the month month in year year; the second one is the number of days in the month. Weekday codes are 0 (Monday) to 6 (Sunday); month numbers are 1 to 12.

calendar.prcal(year,w=2,l=1,c=6)

Like print calendar.calendar(year,w,l,c).


calendar.prmonth(year,month,w=2,l=1)

Like print calendar.month(year,month,w,l).

calendar.setfirstweekday(weekday)

Sets the first day of each week to weekday code weekday. Weekday codes are 0 (Monday) to 6 (Sunday)

calendar.timegm(tupletime)

The inverse of time.gmtime: accepts a time instant in time-tuple form and returns the same instant as a floating-point number of seconds since the epoch.

calendar.weekday(year,month,day)

Returns the weekday code for the given date. Weekday codes are 0 (Monday) to 6 (Sunday); month numbers are 1 (January) to 12 (December).

Other Modules & Functions:
The datetime Module
The pytz Module
The dateutil Module

https://docs.python.org/3/library/datetime.html#module-datetime
http://labix.org/python-dateutil

Functions:

A function is a block of organized, reusable code that is used to perform a single, related action. Functions provide better modularity for your application and a high degree of code reusing.

As you already know, Python gives you many built-in functions like print(), etc. but you can also create your own functions. These functions are called user-defined functions.

Defining a Function
You can define functions to provide the required functionality. Here are simple rules to define a function in Python.

Function blocks begin with the keyword def followed by the function name and parentheses ( ( ) ).

Any input parameters or arguments should be placed within these parentheses. You can also define parameters inside these parentheses.

The first statement of a function can be an optional statement - the documentation string of the function or docstring.

The code block within every function starts with a colon (:) and is indented.

The statement return [expression] exits a function, optionally passing back an expression to the caller. A return statement with no arguments is the same as return None.

Syntax
def functionname( parameters ):
"function_docstring"
function_suite
return [expression]
By default, parameters have a positional behavior and you need to inform them in the same order that they were defined.

ex:
def printme( str ):
   "This prints a passed string into this function"
   print str
   return


Calling a Function
Defining a function only gives it a name, specifies the parameters that are to be included in the function and structures the blocks of code.

Once the basic structure of a function is finalized, you can execute it by calling it from another function or directly from the Python prompt. Following is the example

# Function definition is here
def printme( str ):
   "This prints a passed string into this function"
   print str
   return;

# Now you can call printme function
printme("I'm first call to user defined function!")
printme("Again second call to the same function")


Pass by reference vs value
All parameters (arguments) in the Python language are passed by reference. It means if you change what a parameter refers to within a function, the change also reflects back in the calling function. For example −

# Function definition is here
def changeme( mylist ):
   "This changes a passed list into this function"
   mylist.append([1,2,3,4]);
   print "Values inside the function: ", mylist
   return

# Now you can call changeme function
mylist = [10,20,30];
changeme( mylist );
print "Values outside the function: ", mylist


There is one more example where argument is being passed by reference and the reference is being overwritten inside the called function.

# Function definition is here
def changeme( mylist ):
   "This changes a passed list into this function"
   mylist = [1,2,3,4]; # This would assig new reference in mylist
   print "Values inside the function: ", mylist
   return

# Now you can call changeme function
mylist = [10,20,30];
changeme( mylist );
print "Values outside the function: ", mylist


The parameter mylist is local to the function changeme. Changing mylist within the function does not affect mylist.

Function Arguments
You can call a function by using the following types of formal arguments −

Required arguments
Keyword arguments
Default arguments
Variable-length arguments


Required arguments
Required arguments are the arguments passed to a function in correct positional order. Here, the number of arguments in the function call should match exactly with the function definition.

To call the function printme(), you definitely need to pass one argument, otherwise it gives a syntax error 

Traceback (most recent call last):
File "test.py", line 11, in <module>
printme();
TypeError: printme() takes exactly 1 argument (0 given)

Keyword arguments
Keyword arguments are related to the function calls. When you use keyword arguments in a function call, the caller identifies the arguments by the parameter name.

This allows you to skip arguments or place them out of order because the Python interpreter is able to use the keywords provided to match the values with parameters. You can also make keyword calls to the printme() function in the following ways −

# Function definition is here
def printme( str ):
   "This prints a passed string into this function"
   print str
   return;

# Now you can call printme function
printme( str = "My string")

Note that the order of parameters does not matter.
def printinfo( name, age ):
   "This prints a passed info into this function"
   print "Name: ", name
   print "Age ", age
   return;

# Now you can call printinfo function
printinfo( age=50, name="miki" )

Default arguments
A default argument is an argument that assumes a default value if a value is not provided in the function call for that argument. 


# Function definition is here
def printinfo( name, age = 35 ):
   "This prints a passed info into this function"
   print "Name: ", name
   print "Age ", age
   return;

# Now you can call printinfo function
printinfo( age=50, name="miki" )
printinfo( name="miki" )

Variable-length arguments
You may need to process a function for more arguments than you specified while defining the function. These arguments are called variable-length arguments and are not named in the function definition, unlike required and default arguments.

Syntax for a function with non-keyword variable arguments 

def functionname([formal_args,] *var_args_tuple ):
"function_docstring"
function_suite
return [expression]

An asterisk (*) is placed before the variable name that holds the values of all nonkeyword variable arguments. This tuple remains empty if no additional arguments are specified during the function call.

# Function definition is here
def printinfo( arg1, *vartuple ):
   "This prints a variable passed arguments"
   print "Output is: "
   print arg1
   for var in vartuple:
      print var
   return;

# Now you can call printinfo function
printinfo( 10 )
printinfo( 70, 60, 50 )


The Anonymous Functions
These functions are called anonymous because they are not declared in the standard manner by using the def keyword. You can use the lambda keyword to create small anonymous functions.

Lambda forms can take any number of arguments but return just one value in the form of an expression. They cannot contain commands or multiple expressions.

An anonymous function cannot be a direct call to print because lambda requires an expression

Lambda functions have their own local namespace and cannot access variables other than those in their parameter list and those in the global namespace.

Although it appears that lambda's are a one-line version of a function, they are not equivalent to inline statements in C or C++, whose purpose is by passing function stack allocation during invocation for performance reasons.

Syntax
The syntax of lambda functions contains only a single statement, which is as follows −

lambda [arg1 [,arg2,.....argn]]:expression

Following is the example to show how lambda form of function works:
# Function definition is here
sum = lambda arg1, arg2: arg1 + arg2;

# Now you can call sum as a function
print "Value of total : ", sum( 10, 20 )
print "Value of total : ", sum( 20, 20 )

The return Statement
The statement return [expression] exits a function, optionally passing back an expression to the caller. A return statement with no arguments is the same as return None.

All the above examples are not returning any value.
# Function definition is here
def sum( arg1, arg2 ):
   # Add both the parameters and return them."
   total = arg1 + arg2
   print "Inside the function : ", total
   return total;

# Now you can call sum function
total = sum( 10, 20 );
print "Outside the function : ", total 

Scope of Variables
All variables in a program may not be accessible at all locations in that program. This depends on where you have declared a variable.

The scope of a variable determines the portion of the program where you can access a particular identifier. There are two basic scopes of variables in Python −

Global variables
Local variables
Global vs. Local variables
Variables that are defined inside a function body have a local scope, and those defined outside have a global scope.

This means that local variables can be accessed only inside the function in which they are declared, whereas global variables can be accessed throughout the program body by all functions. When you call a function, the variables declared inside it are brought into scope.

total = 0; # This is global variable.
# Function definition is here
def sum( arg1, arg2 ):
   # Add both the parameters and return them."
   total = arg1 + arg2; # Here total is local variable.
   print "Inside the function local total : ", total
   return total;

# Now you can call sum function
sum( 10, 20 );
print "Outside the function global total : ", total 


Modules:
A module allows you to logically organize your Python code. Grouping related code into a module makes the code easier to understand and use. A module is a Python object with arbitrarily named attributes that you can bind and reference.

Simply, a module is a file consisting of Python code. A module can define functions, classes and variables. A module can also include runnable code.
The Python code for a module named aname normally resides in a file named aname.py. 
def print_func( par ):
   print "Hello : ", par
   return

The import Statement
You can use any Python source file as a module by executing an import statement in some other Python source file
import module1[, module2[,... moduleN]

When the interpreter encounters an import statement, it imports the module if the module is present in the search path. A search path is a list of directories that the interpreter searches before importing a module. 

A module is loaded only once, regardless of the number of times it is imported. This prevents the module execution from happening over and over again if multiple imports occur.

The from...import Statement
Python's from statement lets you import specific attributes from a module into the current namespace. The from...import has the following syntax −

from modname import name1[, name2[, ... nameN]]
For example, to import the function fibonacci from the module fib

from fib import fibonacci


This statement does not import the entire module fib into the current namespace; it just introduces the item fibonacci from the module fib into the global symbol table of the importing module.

The from...import * Statement
It is also possible to import all names from a module into the current namespace by using the following import statement −

from modname import *
This provides an easy way to import all the items from a module into the current namespace; however, this statement should be used sparingly.


Locating Modules
When you import a module, the Python interpreter searches for the module in the following sequences −

The current directory.

If the module isn't found, Python then searches each directory in the shell variable PYTHONPATH.

If all else fails, Python checks the default path. On UNIX, this default path is normally /usr/local/lib/python/.

The module search path is stored in the system module sys as the sys.path variable. The sys.path variable contains the current directory, PYTHONPATH, and the installation-dependent default.

The PYTHONPATH Variable
The PYTHONPATH is an environment variable, consisting of a list of directories. The syntax of PYTHONPATH is the same as that of the shell variable PATH.

Here is a typical PYTHONPATH from a Windows system −

set PYTHONPATH = c:\python20\lib;
And here is a typical PYTHONPATH from a UNIX system −

set PYTHONPATH = /usr/local/lib/python
Namespaces and Scoping
Variables are names (identifiers) that map to objects. A namespace is a dictionary of variable names (keys) and their corresponding objects (values).

A Python statement can access variables in a local namespace and in the global namespace. If a local and a global variable have the same name, the local variable shadows the global variable.

Each function has its own local namespace. Class methods follow the same scoping rule as ordinary functions.

Python makes educated guesses on whether variables are local or global. It assumes that any variable assigned a value in a function is local.

Therefore, in order to assign a value to a global variable within a function, you must first use the global statement.

The statement global VarName tells Python that VarName is a global variable. Python stops searching the local namespace for the variable.

For example, we define a variable Money in the global namespace. Within the function Money, we assign Money a value, therefore Python assumes Money as a local variable. However, we accessed the value of the local variable Money before setting it, so an UnboundLocalError is the result. Uncommenting the global statement fixes the problem.

#!/usr/bin/python

Money = 2000
def AddMoney():
   # Uncomment the following line to fix the code:
   # global Money
   Money = Money + 1

print Money
AddMoney()
print Money

The dir( ) Function:
The dir() built-in function returns a sorted list of strings containing the names defined by a module.

The list contains the names of all the modules, variables and functions that are defined in a module. Following is a simple example −

[ Live Demo](http://tpcg.io/ZoifUr)
#!/usr/bin/python

# Import built-in module math
import math

content = dir(math)
print content


When the above code is executed, it produces the following result −

['__doc__', '__file__', '__name__', 'acos', 'asin', 'atan',
'atan2', 'ceil', 'cos', 'cosh', 'degrees', 'e', 'exp',
'fabs', 'floor', 'fmod', 'frexp', 'hypot', 'ldexp', 'log',
'log10', 'modf', 'pi', 'pow', 'radians', 'sin', 'sinh',
'sqrt', 'tan', 'tanh']
Here, the special string variable __name__ is the module's name, and __file__ is the filename from which the module was loaded.

The globals() and locals() Functions:
The globals() and locals() functions can be used to return the names in the global and local namespaces depending on the location from where they are called.

If locals() is called from within a function, it will return all the names that can be accessed locally from that function.

If globals() is called from within a function, it will return all the names that can be accessed globally from that function.

The return type of both these functions is dictionary. Therefore, names can be extracted using the keys() function.

The reload() Function
When the module is imported into a script, the code in the top-level portion of a module is executed only once.

Therefore, if you want to reexecute the top-level code in a module, you can use the reload() function. The reload() function imports a previously imported module again. The syntax of the reload() function is this −

reload(module_name)
Here, module_name is the name of the module you want to reload and not the string containing the module name. For example, to reload hello module, do the following −

reload(hello)
Packages in Python
A package is a hierarchical file directory structure that defines a single Python application environment that consists of modules and subpackages and sub-subpackages, and so on.

Consider a file Pots.py available in Phone directory. This file has following line of source code −

#!/usr/bin/python

def Pots():
   print "I'm Pots Phone"
Similar way, we have another two files having different functions with the same name as above −

Phone/Isdn.py file having function Isdn()

Phone/G3.py file having function G3()

Now, create one more file __init__.py in Phone directory −

Phone/__init__.py
**To make all of your functions available when you've imported Phone, you need to put explicit import statements in __init__.py as follows −**

from Pots import Pots
from Isdn import Isdn
from G3 import G3
After you add these lines to __init__.py, you have all of these classes available when you import the Phone package.

#!/usr/bin/python

# Now import your Phone Package.
import Phone

Phone.Pots()
Phone.Isdn()
Phone.G3()


In the above example, we have taken example of a single functions in each file, but you can keep multiple functions in your files. You can also define different Python classes in those files and then you can create your packages out of those classes.

Files I/O:
Printing to the Screen -
simplest way to produce output is using the print statement where you can pass zero or more expressions separated by commas. This function converts the expressions you pass into a string and writes the result to standard output as follows
print "Python is really a great language,", "isn't it?"

Reading Keyboard Input
Python provides two built-in functions to read a line of text from standard input, which by default comes from the keyboard. These functions are −

raw_input
input

Reading Keyboard Input
Python provides two built-in functions to read a line of text from standard input, which by default comes from the keyboard. These functions are −

raw_input
input
The raw_input Function
The raw_input([prompt]) function reads one line from standard input and returns it as a string (removing the trailing newline).

#!/usr/bin/python

str = raw_input("Enter your input: ")
print "Received input is : ", str

The input Function
The input([prompt]) function is equivalent to raw_input, except that it assumes the input is a valid Python expression and returns the evaluated result to you.

str = input("Enter your input: ")
print "Received input is : ", str

This would produce the following result against the entered input −

Enter your input: [x*5 for x in range(2,10,2)]
Recieved input is : [10, 20, 30, 40]

Opening and Closing Files
Until now, you have been reading and writing to the standard input and output. Now, we will see how to use actual data files.

Python provides basic functions and methods necessary to manipulate files by default. You can do most of the file manipulation using a file object.

The open Function
Before you can read or write a file, you have to open it using Python's built-in open() function. This function creates a file object, which would be utilized to call other support methods associated with it.

Syntax
file object = open(file_name [, access_mode][, buffering])
Here are parameter details −

file_name − The file_name argument is a string value that contains the name of the file that you want to access.

access_mode − The access_mode determines the mode in which the file has to be opened, i.e., read, write, append, etc. A complete list of possible values is given below in the table. This is optional parameter and the default file access mode is read (r).

buffering − If the buffering value is set to 0, no buffering takes place. If the buffering value is 1, line buffering is performed while accessing a file. If you specify the buffering value as an integer greater than 1, then buffering action is performed with the indicated buffer size. If negative, the buffer size is the system default(default behavior).1	
r

Opens a file for reading only. The file pointer is placed at the beginning of the file. This is the default mode.

2	
rb

Opens a file for reading only in binary format. The file pointer is placed at the beginning of the file. This is the default mode.

3	
r+

Opens a file for both reading and writing. The file pointer placed at the beginning of the file.

4	
rb+

Opens a file for both reading and writing in binary format. The file pointer placed at the beginning of the file.

5	
w

Opens a file for writing only. Overwrites the file if the file exists. If the file does not exist, creates a new file for writing.

6	
wb

Opens a file for writing only in binary format. Overwrites the file if the file exists. If the file does not exist, creates a new file for writing.

7	
w+

Opens a file for both writing and reading. Overwrites the existing file if the file exists. If the file does not exist, creates a new file for reading and writing.

8	
wb+

Opens a file for both writing and reading in binary format. Overwrites the existing file if the file exists. If the file does not exist, creates a new file for reading and writing.

9	
a

Opens a file for appending. The file pointer is at the end of the file if the file exists. That is, the file is in the append mode. If the file does not exist, it creates a new file for writing.

10	
ab

Opens a file for appending in binary format. The file pointer is at the end of the file if the file exists. That is, the file is in the append mode. If the file does not exist, it creates a new file for writing.

11	
a+

Opens a file for both appending and reading. The file pointer is at the end of the file if the file exists. The file opens in the append mode. If the file does not exist, it creates a new file for reading and writing.

12	
ab+

Opens a file for both appending and reading in binary format. The file pointer is at the end of the file if the file exists. The file opens in the append mode. If the file does not exist, it creates a new file for reading and writing.


The file Object Attributes
Once a file is opened and you have one file object, you can get various information related to that file.
Here is a list of all attributes related to file object −
file.closed: returns true if file is closed, false otherwise
file.mode: returns access mode with which file was opened
file.name: returns name of the file
file.softspace: returns false if space explicitly required with print, true otherwise

fo = open("foo.txt", "wb")
print "Name of the file: ", fo.name
print "Closed or not : ", fo.closed
print "Opening mode : ", fo.mode
print "Softspace flag : ", fo.softspace

The close() Method
The close() method of a file object flushes any unwritten information and closes the file object, after which no more writing can be done.

Python automatically closes a file when the reference object of a file is reassigned to another file. It is a good practice to use the close() method to close a file.
fileObject.close()


# Open a file
fo = open("foo.txt", "wb")
print "Name of the file: ", fo.name

# Close opend file
fo.close()

Reading and Writing Files
The file object provides a set of access methods to make our lives easier. We would see how to use read() and write() methods to read and write files.

The write() Method
The write() method writes any string to an open file. It is important to note that Python strings can have binary data and not just text.

The write() method does not add a newline character ('\n') to the end of the string
fileObject.write(string)


# Open a file
fo = open("foo.txt", "wb")
fo.write( "Python is a great language.\nYeah its great!!\n")

# Close opend file
fo.close()
The above method would create foo.txt file and would write given content in that file and finally it would close that file. If you would open this file, it would have following content.

Python is a great language.
Yeah its great!!
The read() Method
The read() method reads a string from an open file. It is important to note that Python strings can have binary data. apart from text data.

Syntax
fileObject.read([count])

Here, passed parameter is the number of bytes to be read from the opened file. This method starts reading from the beginning of the file and if count is missing, then it tries to read as much as possible, maybe until the end of file.

Example
Let's take a file foo.txt, which we created above.

#!/usr/bin/python

# Open a file
fo = open("foo.txt", "r+")
str = fo.read(10);
print "Read String is : ", str
# Close opend file
fo.close()

File Positions
The tell() method tells you the current position within the file; in other words, the next read or write will occur at that many bytes from the beginning of the file.

The seek(offset[, from]) method changes the current file position. The offset argument indicates the number of bytes to be moved. The from argument specifies the reference position from where the bytes are to be moved.

If from is set to 0, it means use the beginning of the file as the reference position and 1 means use the current position as the reference position and if it is set to 2 then the end of the file would be taken as the reference position.



# Open a file
fo = open("foo.txt", "r+")
str = fo.read(10)
print "Read String is : ", str

# Check current position
position = fo.tell()
print "Current file position : ", position

# Reposition pointer at the beginning once again
position = fo.seek(0, 0);
str = fo.read(10)
print "Again read String is : ", str
# Close opend file
fo.close()


Renaming and Deleting Files
Python os module provides methods that help you perform file-processing operations, such as renaming and deleting files.

To use this module you need to import it first and then you can call any related functions.

The rename() Method
The rename() method takes two arguments, the current filename and the new filename.

Syntax
os.rename(current_file_name, new_file_name)


import os

# Rename a file from test1.txt to test2.txt
os.rename( "test1.txt", "test2.txt" )


The remove() Method
You can use the remove() method to delete files by supplying the name of the file to be deleted as the argument.

Syntax
os.remove(file_name)


import os

# Delete file test2.txt
os.remove("text2.txt")


Directories in Python
All files are contained within various directories, and Python has no problem handling these too. The os module has several methods that help you create, remove, and change directories.

The mkdir() Method
You can use the mkdir() method of the os module to create directories in the current directory. You need to supply an argument to this method which contains the name of the directory to be created.

Syntax
os.mkdir("newdir")


import os

# Create a directory "test"
os.mkdir("test")


The chdir() Method
You can use the chdir() method to change the current directory. The chdir() method takes an argument, which is the name of the directory that you want to make the current directory.

Syntax
os.chdir("newdir")

import os

# Changing a directory to "/home/newdir"
os.chdir("/home/newdir")


The getcwd() Method
The getcwd() method displays the current working directory.

Syntax
os.getcwd()


import os

# This would give location of the current directory
os.getcwd()
The rmdir() Method
The rmdir() method deletes the directory, which is passed as an argument in the method.

Before removing a directory, all the contents in it should be removed.

Syntax
os.rmdir('dirname')


It is required to give fully qualified name of the directory, otherwise it would search for that directory in the current directory.


import os

# This would  remove "/tmp/test"  directory.
os.rmdir( "/tmp/test"  )

There are three important sources, which provide a wide range of utility methods to handle and manipulate files & directories on Windows and Unix operating systems. They are as follows −

File Object Methods: The file object provides functions to manipulate files.
A file object is created using open function and here is a list of functions which can be called on this object −
file.close()
Close the file. A closed file cannot be read or written any more.

file.flush()
Flush the internal buffer, like stdio's fflush. This may be a no-op on some file-like objects.

file.fileno()
Returns the integer file descriptor that is used by the underlying implementation to request I/O operations from the operating system.

file.isatty()
Returns True if the file is connected to a tty(-like) device, else False.

file.next()
Returns the next line from the file each time it is being called.

file.read([size])
Reads at most size bytes from the file (less if the read hits EOF before obtaining size bytes).

file.readline([size])
Reads one entire line from the file. A trailing newline character is kept in the string.

file.readlines([sizehint])
Reads until EOF using readline() and return a list containing the lines. If the optional sizehint argument is present, instead of reading up to EOF, whole lines totalling approximately sizehint bytes (possibly after rounding up to an internal buffer size) are read.

file.seek(offset[, whence])
Sets the file's current position

file.tell()
Returns the file's current position

file.truncate([size])
Truncates the file's size. If the optional size argument is present, the file is truncated to (at most) that size.

file.write(str)
Writes a string to the file. There is no return value.

file.writelines(sequence)
Writes a sequence of strings to the file. The sequence can be any iterable object producing strings, typically a list of strings.


OS Object Methods: This provides methods to process files as well as directories.
https://www.tutorialspoint.com/python/os_file_methods.htm

Python Standard Exceptions:
Exceptions Handling:
two very important features to handle any unexpected error in your Python programs and to add debugging capabilities in them −

Exception Handling −
list standard Exceptions available in Python: 
Exception Base class for all exceptions
StopIteration Raised when the next() method of an iterator does not point to any object.
SystemExit Raised by the sys.exit() function.
StandardError Base class for all built-in exceptions except StopIteration and SystemExit.
ArithmeticError Base class for all errors that occur for numeric calculation.
OverflowError Raised when a calculation exceeds maximum limit for a numeric type.
FloatingPointError Raised when a floating point calculation fails.
ZeroDivisionError Raised when division or modulo by zero takes place for all numeric types.
AssertionError Raised in case of failure of the Assert statement.
AttributeError Raised in case of failure of attribute reference or assignment.
EOFError Raised when there is no input from either the raw_input() or input() function and the end of file is reached.
ImportError Raised when an import statement fails.
KeyboardInterrupt Raised when the user interrupts program execution, usually by pressing Ctrl+c.
LookupError Base class for all lookup errors.
IndexError Raised when an index is not found in a sequence.
KeyError Raised when the specified key is not found in the dictionary.
NameError Raised when an identifier is not found in the local or global namespace.
UnboundLocalError Raised when trying to access a local variable in a function or method but no value has been assigned to it.
EnvironmentError Base class for all exceptions that occur outside the Python environment.
IOError Raised when an input/ output operation fails, such as the print statement or the open() function when trying to open a file that does not exist.
OSError Raised for operating system-related errors.
SyntaxError Raised when there is an error in Python syntax.
IndentationError Raised when indentation is not specified properly.
SystemError Raised when the interpreter finds an internal problem, but when this error is encountered the Python interpreter does not exit.
SystemExit Raised when Python interpreter is quit by using the sys.exit() function. If not handled in the code, causes the interpreter to exit.
TypeError Raised when an operation or function is attempted that is invalid for the specified data type.
ValueError Raised when the built-in function for a data type has the valid type of arguments, but the arguments have invalid values specified.
RuntimeError Raised when a generated error does not fall into any category.
NotImplementedError Raised when an abstract method that needs to be implemented in an inherited class is not actually implemented.


Assertions −
An assertion is a sanity-check that you can turn on or turn off when you are done with your testing of the program.

The easiest way to think of an assertion is to liken it to a raise-if statement (or to be more accurate, a raise-if-not statement). An expression is tested, and if the result comes up false, an exception is raised.

Programmers often place assertions at the start of a function to check for valid input, and after a function call to check for valid output.



The assert Statement
When it encounters an assert statement, Python evaluates the accompanying expression, which is hopefully true. If the expression is false, Python raises an AssertionError exception.

The syntax for assert is −

assert Expression[, Arguments]
If the assertion fails, Python uses ArgumentExpression as the argument for the AssertionError. AssertionError exceptions can be caught and handled like any other exception using the try-except statement, but if not handled, they will terminate the program and produce a traceback.


ex:
def KelvinToFahrenheit(Temperature):
   assert (Temperature >= 0),"Colder than absolute zero!"
   return ((Temperature-273)*1.8)+32

print KelvinToFahrenheit(273)
print int(KelvinToFahrenheit(505.78))
print KelvinToFahrenheit(-5)


An assertion is a sanity-check that you can turn on or turn off when you are done with your testing of the program.

The easiest way to think of an assertion is to liken it to a raise-if statement (or to be more accurate, a raise-if-not statement). An expression is tested, and if the result comes up false, an exception is raised.

Programmers often place assertions at the start of a function to check for valid input, and after a function call to check for valid output.

The assert Statement
When it encounters an assert statement, Python evaluates the accompanying expression, which is hopefully true. If the expression is false, Python raises an AssertionError exception.


assert Expression[, Arguments]

when a Python script encounters a situation that it cannot cope with, it raises an exception. An exception is a Python object that represents an error.

When a Python script raises an exception, it must either handle the exception immediately otherwise it terminates and quits.


Handling an exception
If you have some suspicious code that may raise an exception, you can defend your program by placing the suspicious code in a try: block. After the try: block, include an except: statement, followed by a block of code which handles the problem as elegantly as possible.


 try....except...else blocks

A single try statement can have multiple except statements. This is useful when the try block contains statements that may throw different types of exceptions.

You can also provide a generic except clause, which handles any exception.

After the except clause(s), you can include an else-clause. The code in the else-block executes if the code in the try: block does not raise an exception.

The else-block is a good place for code that does not need the try: block's protection.


try:
   fh = open("testfile", "w")
   fh.write("This is my test file for exception handling!!")
except IOError:
   print "Error: can\'t find file or read data"
else:
   print "Written content in the file successfully"
   fh.close()


The except Clause with No Exceptions
You can also use the except statement with no exceptions defined as follows −

try:
You do your operations here;
......................
except:
If there is any exception, then execute this block.
......................
else:
If there is no exception then execute this block.
This kind of a try-except statement catches all the exceptions that occur. Using this kind of try-except statement is not considered a good programming practice though, because it catches all exceptions but does not make the programmer identify the root cause of the problem that may occur.


The except Clause with Multiple Exceptions
You can also use the same except statement to handle multiple exceptions as follows −

try:
   You do your operations here;
   ......................
except(Exception1[, Exception2[,...ExceptionN]]]):
   If there is any exception from the given exception list, 
   then execute this block.
   ......................
else:
   If there is no exception then execute this block. 


The try-finally Clause
You can use a finally: block along with a try: block. The finally block is a place to put any code that must execute, whether the try-block raised an exception or not. The syntax of the try-finally statement is this −

try:
   You do your operations here;
   ......................
   Due to any exception, this may be skipped.
finally:
   This would always be executed.
   ......................


**You cannot use else clause as well along with a finally clause.**



try:
   fh = open("testfile", "w")
   try:
      fh.write("This is my test file for exception handling!!")
   finally:
      print "Going to close the file"
      fh.close()
except IOError:
   print "Error: can\'t find file or read data"


When an exception is thrown in the try block, the execution immediately passes to the finally block. After all the statements in the finally block are executed, the exception is raised again and is handled in the except statements if present in the next higher layer of the try-except statement.

Argument of an Exception
An exception can have an argument, which is a value that gives additional information about the problem. The contents of the argument vary by exception. You capture an exception's argument by supplying a variable in the except clause as follows −

try:
   You do your operations here;
   ......................
except ExceptionType, Argument:
   You can print value of Argument here...



If you write the code to handle a single exception, you can have a variable follow the name of the exception in the except statement. If you are trapping multiple exceptions, you can have a variable follow the tuple of the exception.

This variable receives the value of the exception mostly containing the cause of the exception. The variable can receive a single value or multiple values in the form of a tuple. This tuple usually contains the error string, the error number, and an error location.

def temp_convert(var):
   try:
      return int(var)
   except ValueError, Argument:
      print "The argument does not contain numbers\n", Argument

# Call above function here.
temp_convert("xyz");

Raising an Exceptions
You can raise exceptions in several ways by using the raise statement. The general syntax for the raise statement is as follows.

Syntax
raise [Exception [, args [, traceback]]]
Here, Exception is the type of exception (for example, NameError) and argument is a value for the exception argument. The argument is optional; if not supplied, the exception argument is None.

The final argument, traceback, is also optional (and rarely used in practice), and if present, is the traceback object used for the exception.

Example
An exception can be a string, a class or an object. Most of the exceptions that the Python core raises are classes, with an argument that is an instance of the class. Defining new exceptions is quite easy and can be done as follows −

def functionName( level ):
   if level < 1:
      raise "Invalid level!", level

Note: In order to catch an exception, an "except" clause must refer to the same exception thrown either class object or simple string. For example, to capture above exception, we must write the except clause as follows −

try:
   Business Logic here...
except "Invalid level!":
   Exception handling here...
else:
   Rest of the code here...
User-Defined Exceptions
Python also allows you to create your own exceptions by deriving classes from the standard built-in exceptions.

Here is an example related to RuntimeError. Here, a class is created that is subclassed from RuntimeError. This is useful when you need to display more specific information when an exception is caught.

In the try block, the user-defined exception is raised and caught in the except block. The variable e is used to create an instance of the class Networkerror.

class Networkerror(RuntimeError):
   def __init__(self, arg):
      self.args = arg
So once you defined above class, you can raise the exception as follows −

try:
   raise Networkerror("Bad hostname")
except Networkerror,e:
   print e.args





```

**Object Oriented:**
```
Python has been an object-oriented language since it existed. Because of this, creating and using classes and objects are downright easy. 

Overview of OOP Terminology:

Class − A user-defined prototype for an object that defines a set of attributes that characterize any object of the class. The attributes are data members (class variables and instance variables) and methods, accessed via dot notation.

Class variable − A variable that is shared by all instances of a class. Class variables are defined within a class but outside any of the class's methods. Class variables are not used as frequently as instance variables are.

Data member − A class variable or instance variable that holds data associated with a class and its objects.

Function overloading − The assignment of more than one behavior to a particular function. The operation performed varies by the types of objects or arguments involved.

Instance variable − A variable that is defined inside a method and belongs only to the current instance of a class.

Inheritance − The transfer of the characteristics of a class to other classes that are derived from it.

Instance − An individual object of a certain class. An object obj that belongs to a class Circle, for example, is an instance of the class Circle.

Instantiation − The creation of an instance of a class.

Method − A special kind of function that is defined in a class definition.

Object − A unique instance of a data structure that's defined by its class. An object comprises both data members (class variables and instance variables) and methods.

Operator overloading − The assignment of more than one function to a particular operator.

Creating Classes
The class statement creates a new class definition. The name of the class immediately follows the keyword class followed by a colon as follows −

class ClassName:
'Optional class documentation string'
class_suite
The class has a documentation string, which can be accessed via ClassName.__doc__.

The class_suite consists of all the component statements defining class members, data attributes and functions.

class Employee:
   'Common base class for all employees'
   empCount = 0

   def __init__(self, name, salary):
      self.name = name
      self.salary = salary
      Employee.empCount += 1
   
   def displayCount(self):
     print "Total Employee %d" % Employee.empCount

   def displayEmployee(self):
      print "Name : ", self.name,  ", Salary: ", self.salary


The variable empCount is a class variable whose value is shared among all instances of a this class. This can be accessed as Employee.empCount from inside the class or outside the class.

The first method __init__() is a special method, which is called class constructor or initialization method that Python calls when you create a new instance of this class.

You declare other class methods like normal functions with the exception that the first argument to each method is self. Python adds the self argument to the list for you; you do not need to include it when you call the methods.

Creating Instance Objects
To create instances of a class, you call the class using class name and pass in whatever arguments its __init__ method accepts.

"This would create first object of Employee class"
emp1 = Employee("Zara", 2000)
"This would create second object of Employee class"
emp2 = Employee("Manni", 5000)
Accessing Attributes
You access the object's attributes using the dot operator with object. Class variable would be accessed using class name as follows −

emp1.displayEmployee()
emp2.displayEmployee()
print "Total Employee %d" % Employee.empCount
Now, putting all the concepts together −

#!/usr/bin/python

class Employee:
   'Common base class for all employees'
   empCount = 0

   def __init__(self, name, salary):
      self.name = name
      self.salary = salary
      Employee.empCount += 1
   
   def displayCount(self):
     print "Total Employee %d" % Employee.empCount

   def displayEmployee(self):
      print "Name : ", self.name,  ", Salary: ", self.salary

"This would create first object of Employee class"
emp1 = Employee("Zara", 2000)
"This would create second object of Employee class"
emp2 = Employee("Manni", 5000)
emp1.displayEmployee()
emp2.displayEmployee()
print "Total Employee %d" % Employee.empCount



Instead of using the normal statements to access attributes, you can use the following functions −

The getattr(obj, name[, default]) − to access the attribute of object.
The hasattr(obj,name) − to check if an attribute exists or not.
The setattr(obj,name,value) − to set an attribute. If attribute does not exist, then it would be created.
The delattr(obj, name) − to delete an attribute.

hasattr(emp1, 'age') # Returns true if 'age' attribute exists
getattr(emp1, 'age') # Returns value of 'age' attribute
setattr(emp1, 'age', 8) # Set attribute 'age' at 8
delattr(empl, 'age') # Delete attribute 'age'


Built-in class Attributes:

Every Python class keeps following built-in attributes and they can be accessed using dot operator like any other attribute −

__dict__ − Dictionary containing the class's namespace.
__doc__ − Class documentation string or none, if undefined.
__name__ − Class name.
__module__ − Module name in which the class is defined. This attribute is "__main__" in interactive mode.
__bases__ − A possibly empty tuple containing the base classes, in the order of their occurrence in the base class list.


Destroying Objects (Garbage Collection)
Python deletes unneeded objects (built-in types or class instances) automatically to free the memory space. The process by which Python periodically reclaims blocks of memory that no longer are in use is termed Garbage Collection.

Python's garbage collector runs during program execution and is triggered when an object's reference count reaches zero. An object's reference count changes as the number of aliases that point to it changes.

An object's reference count increases when it is assigned a new name or placed in a container (list, tuple, or dictionary). The object's reference count decreases when it's deleted with del, its reference is reassigned, or its reference goes out of scope. When an object's reference count reaches zero, Python collects it automatically.


Note − Ideally, you should define your classes in separate file, then you should import them in your main program file using import statement.

Class Inheritance
Instead of starting from scratch, you can create a class by deriving it from a preexisting class by listing the parent class in parentheses after the new class name.

The child class inherits the attributes of its parent class, and you can use those attributes as if they were defined in the child class. A child class can also override data members and methods from the parent.

Syntax
Derived classes are declared much like their parent class; however, a list of base classes to inherit from is given after the class name −

class SubClassName (ParentClass1[, ParentClass2, ...]):
   'Optional class documentation string'
   class_suite
Example

#!/usr/bin/python

class Parent:        # define parent class
   parentAttr = 100
   def __init__(self):
      print "Calling parent constructor"

   def parentMethod(self):
      print 'Calling parent method'

   def setAttr(self, attr):
      Parent.parentAttr = attr

   def getAttr(self):
      print "Parent attribute :", Parent.parentAttr

class Child(Parent): # define child class
   def __init__(self):
      print "Calling child constructor"

   def childMethod(self):
      print 'Calling child method'

c = Child()          # instance of child
c.childMethod()      # child calls its method
c.parentMethod()     # calls parent's method
c.setAttr(200)       # again call parent's method
c.getAttr()          # again call parent's method


You normally will not notice when the garbage collector destroys an orphaned instance and reclaims its space. But a class can implement the special method __del__(), called a destructor, that is invoked when the instance is about to be destroyed. This method might be used to clean up any non memory resources used by an instance.

Example
This __del__() destructor prints the class name of an instance that is about to be destroyed −


#!/usr/bin/python

class Point:
   def __init__( self, x=0, y=0):
      self.x = x
      self.y = y
   def __del__(self):
      class_name = self.__class__.__name__
      print class_name, "destroyed"

pt1 = Point()
pt2 = pt1
pt3 = pt1
print id(pt1), id(pt2), id(pt3) # prints the ids of the obejcts
del pt1
del pt2
del pt3



Note − Ideally, you should define your classes in separate file, then you should import them in your main program file using import statement.

Class Inheritance:
Instead of starting from scratch, you can create a class by deriving it from a preexisting class by listing the parent class in parentheses after the new class name.

The child class inherits the attributes of its parent class, and you can use those attributes as if they were defined in the child class. A child class can also override data members and methods from the parent.

Syntax
Derived classes are declared much like their parent class; however, a list of base classes to inherit from is given after the class name −

class SubClassName (ParentClass1[, ParentClass2, ...]):
   'Optional class documentation string'
   class_suite
Example
#!/usr/bin/python

class Parent:        # define parent class
   parentAttr = 100
   def __init__(self):
      print "Calling parent constructor"

   def parentMethod(self):
      print 'Calling parent method'

   def setAttr(self, attr):
      Parent.parentAttr = attr

   def getAttr(self):
      print "Parent attribute :", Parent.parentAttr

class Child(Parent): # define child class
   def __init__(self):
      print "Calling child constructor"

   def childMethod(self):
      print 'Calling child method'

c = Child()          # instance of child
c.childMethod()      # child calls its method
c.parentMethod()     # calls parent's method
c.setAttr(200)       # again call parent's method
c.getAttr()          # again call parent's method


You can use issubclass() or isinstance() functions to check a relationships of two classes and instances.

The issubclass(sub, sup) boolean function returns true if the given subclass sub is indeed a subclass of the superclass sup.

The isinstance(obj, Class) boolean function returns true if obj is an instance of class Class or is an instance of a subclass of Class

Overriding Methods
You can always override your parent class methods. One reason for overriding parent's methods is because you may want special or different functionality in your subclass.

Example

#!/usr/bin/python

class Parent:        # define parent class
   def myMethod(self):
      print 'Calling parent method'

class Child(Parent): # define child class
   def myMethod(self):
      print 'Calling child method'

c = Child()          # instance of child
c.myMethod()         # child calls overridden method


Base Overloading Methods
Following table lists some generic functionality that you can override in your own classes −
__init__ ( self [,args...] )
Constructor (with any optional arguments)
Sample Call : obj = className(args)

__del__( self )
Destructor, deletes an object
Sample Call : del obj

__repr__( self )
Evaluable string representation
Sample Call : repr(obj)

__str__( self )
Printable string representation
Sample Call : str(obj)

__cmp__ ( self, x )
Object comparison
Sample Call : cmp(obj, x)



Overloading Operators
Suppose you have created a Vector class to represent two-dimensional vectors, what happens when you use the plus operator to add them? Most likely Python will yell at you.

You could, however, define the __add__ method in your class to perform vector addition and then the plus operator would behave as per expectation −


class Vector:
   def __init__(self, a, b):
      self.a = a
      self.b = b

   def __str__(self):
      return 'Vector (%d, %d)' % (self.a, self.b)
   
   def __add__(self,other):
      return Vector(self.a + other.a, self.b + other.b)

v1 = Vector(2,10)
v2 = Vector(5,-2)
print v1 + v2



Data Hiding
An object's attributes may or may not be visible outside the class definition. You need to name attributes with a double underscore prefix, and those attributes then are not be directly visible to outsiders.


class JustCounter:
   __secretCount = 0
  
   def count(self):
      self.__secretCount += 1
      print self.__secretCount

counter = JustCounter()
counter.count()
counter.count()
print counter.__secretCount  #gets exception

Python protects those members by internally changing the name to include the class name. You can access such attributes as object._className__attrName. If you would replace your last line as following, then it works for you −

.........................
print counter._JustCounter__secretCount



```


**Regular Expressions:**
```

Regular Expressions:
A regular expression is a special sequence of characters that helps you match or find other strings or sets of strings, using a specialized syntax held in a pattern. Regular expressions are widely used in UNIX world.

The Python module re provides full support for Perl-like regular expressions in Python. The re module raises the exception re.error if an error occurs while compiling or using a regular expression.

We would cover two important functions, which would be used to handle regular expressions. But a small thing first: There are various characters, which would have special meaning when they are used in regular expression. To avoid any confusion while dealing with regular expressions, we would use Raw Strings as r'expression'.

The match Function
This function attempts to match RE pattern to string with optional flags.

Here is the syntax for this function −

re.match(pattern, string, flags=0)

	
pattern
This is the regular expression to be matched.

string
This is the string, which would be searched to match the pattern at the beginning of string.

flags
You can specify different flags using bitwise OR (|). These are modifiers, which are listed in the table below.

The re.match function returns a match object on success, None on failure. We usegroup(num) or groups() function of match object to get matched expression.

group(num=0)
This method returns entire match (or specific subgroup num)

groups()
This method returns all matching subgroups in a tuple (empty if there weren't any)

import re

line = "Cats are smarter than dogs"

matchObj = re.match( r'(.*) are (.*?) .*', line, re.M|re.I)

if matchObj:
   print "matchObj.group() : ", matchObj.group()
   print "matchObj.group(1) : ", matchObj.group(1)
   print "matchObj.group(2) : ", matchObj.group(2)
else:
   print "No match!!"

The search Function:





```
