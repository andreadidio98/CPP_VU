


The Sections of this page marked as *(EXTRA)* are **NOT** essential for passing the course, however they do give a greater insight on the C++ language, and might help you in future courses. Students who are not interested in going the "extra mile" can safely ignore these sections.

# Contents

[Module 1](#module1)

[Module 2](#module2)

[Module 3](#module3)

[Module 4](#module4)

[Module 5](#module5)

[Module 6](#module6)

[Module 7](#module7)

* * *

# <a name="module1"></a>Module 1

>“A journey of a thousand miles begins with a single step.”

## Compiling from the command line

Compiling from the command line is a fairly straight-forward task. The most common C++ compiler (and the one I recommend
using) is the GNU *C++ Compiler* "**g++**". The **DASH** system has a "UNIX-style command line", and compiling is done with the following command (*shell instruction*):
```shell

g++ <c++_source_code_file> -o <target_output_file>

#Example:

g++ hello_world.cpp -o hello_world

```
Running your output file (as an executable), is just as easy:

```shell

./<target_output_file> <optional_parameters>

#Example:

./hello_world

```

## Data Types


#### Primitive Data Types

| Type                   | Keyword           |
|:-----------------------|:------------------|
| Boolean                | bool              |
| Character              | char              |
| Integer                | int               |
| Floating Point         | float             |
| Double Floating Point  | double            |
| Valueless              | void              |
| Wide Character         | wchar_t           |

**NOTE:** Several of these types can be modified using the following modifiers:

* signed
* unsigned
* long
* short

By default, primitive data types are **signed**

#### Types & Their Sizes

| Type            | Typical Size    | Value Range      |
|:----------------|:----------------|:-----------------|
| unsigned char   | 1 Byte          | 0 ~ 255          |
| signed char     | 1 Byte          | -147 ~ 147       |
| unsigned int    | 4 Bytes         | 0 ~ 4294967295   |
| signed int      | 4 Bytes         | -2147483648 ~ 2147483647 |
| short int       | 2 Bytes         | -32768 ~ 32767   |
| long int        | 4 Bytes         | -2147483648 ~ 2147483647 |
| float           | 4 Bytes         | +/- 3.4e +/- 38 (~7 digits) |
| double          | 8 Bytes         | +/- 1.7e +/- 308 (~15 digits) |

**NOTE:** The size of *int* is machine-dependent and is *NOT* guaranteed to be 4 Bytes.

## Variables

We can't make anything of interest with a computer without storing data in memory. We store data in **objects**. To access an object, we give it a *name*. A named object is called a **variable** and has a specific **type**. The data we store in variables are called *values*. A statement that defines a variable is called a **variable definition** and according to latest C++ standards should be **initialised**. An example is:

```c++

int total_days = 365;
char grade = 'A';
std::string name = "John";
bool is_raining = true;
double pi = 3.1415926;
float points = 3.5f; //the final 'f' is optional

```

Notice how a character is enclosed in *single quotes* whilst strings are enclosed in *double quotes*. **NB:** strings are a collection (array) of characters. **(EXTRA)** In fact, the classic way to declare a string in the C programming language, is:

 ```c++

const char* name = "John"; // = std::string name = "John";

```

which essentially is just a **pointer** (See Module 7) to the first character in memory of the string.

There is also a special type of variable which is called a **constant**, as the name suggests, a constant is a variable that we need to use throughout the program but remains unchanged during execution. By convention, constant variables have their names in **capital letters**. For example:

```c++
const int DAYS_OF_THE_YEAR = 365;
constexpr int DAYS_OF_THE_YEAR = 365;//PREFERRED because compile-time constant
//OR EQUIVALENTLY USING THE PREPROCESSOR
#define DAYS_OF_THE_YEAR 365

```

The second method is a **macro**  and is sometimes discouraged in C++ especially for ease of debugging, as the #define instruction, makes the preprocessor (See EXTRA if interested) replace all the occurrences of "DAYS_OF_THE_YEAR" with "365" in the code at the *pre-compilation* stage. This means that if this causes an error, it may be confusing as the compiler trace will show the value and not the name of the macro.

**NOTE:** C++ IS A STRONGLY-TYPED LANGUAGE!!! This means that assigning a value to a variable that does not correspond to the **type** of the variable will cause a **compile-time error**.


## Operators

In C++, there are many built-in operators and are divided into 6 main categories:

1. Arithmetic Operators (+, -, \*, /, %, ++, --)
2. Relational Operators (==, !=, <, >, <=, >=)
3. Bitwise Operators (&, \|, ^, ~, \<\<, \>\>)
4. Logical Operators (&&, \|\|, !)
5. Assignment Operators (=, +=, -=, \*=, /=, %=, &=, \<\<=, \>\>=, \|=, ^=)
6. Misc Operators (sizeof, ., ->, &, \*, Cast, *Ternary*)

The Arithmetic operators, are fairly straight-forward and most, behave as expected. The only two operators that might need a brief explanation are the **Modulo** (**%**) operator, which is a binary operator (takes two "arguments") that returns the remainder of the division operation on two numbers. E.g., 20 % 3 evaluates to 2. The **increment/decrement** (**++/-\-**) are unary operators, and can be used as a *prefix* OR *suffix*. If these operators are placed *before* the variable, the variable is incremented/decremented and THEN used as the incremented/decremented value. For example:

```c++
int a = 20;
int b = 3;

int remainder = (a % b);// = 2

a++; //a = 21
--b; //b = 2

```

The relational operators are mainly used for conditions in control flow statements (See Module 2), *!=* translates to "not equal", where the **!** character is used as the *"Logical NOT"*, and the other operators should be straight-forward.

**NOTE:** The *==* operator is used for the *comparison* of two variables (values) and **NOT** to assign a value to a variable.

The Bitwise operators are used to perform operations on values at the **bit level** and are mentioned here for completeness but are out of the scope of this course.

The Logical operators are used in order to evaluate expressions to obtain a single relational result. For example:

```c++
   int a = 2;
   int b = 3;
   int c = 42;

   bool true_and = (a == 2) && (b == 3);
   bool false_and = (a == 2) && (c == 3);

   bool true_or = (a == 2) || (c == 3);
   bool false_or = (a == 3) || (b == 2);

   bool make_false = !(true_and);
```

The Assignment operators modify the current value of a variable by performing an operation on it. They are equivalent to assigning the result of an operation to the first operand.

The Misc operators you will have to use mainly further along the course (Modules 6 and 7). The sizeof operator, takes an argument which is usually a type (int, char, double etc...), and returns the size in **bytes**, e.g., *sizeof(char)* returns *1*. The dot (.) and arrow (->) operators are used to access class members (Module 6), and the difference is that we use the arrow operator only when we access a class member through a pointer (Module 7). The reference operator (&) returns the address in memory of a variable. The pointer operator (\*) is used both to declare a pointer and to de-reference it, i.e., to grab the value stored at the memory address pointed to by the pointer (more on that in Module 7). The Cast operator is used to cast a variable from one type to another. Finally, the *Ternary* operator (? :) is used to return a value depending on a condition, e.g., *Condition ? X : Y* which means If Condition is true ? then it returns value X : otherwise value Y.

The comma operator is also very useful, and you'll find yourself using it over and over in order to shorter your code. When declaring variables of the *same* type, it is possible to "chain" the declarations using the comma operator as follows:

```c++

int first = 0, second = 0, third = 0;

```

## Type Conversions

There are **Safe** and **Unsafe** type conversions in C++, and unsurprisingly you MUST AVOID unsafe type conversions to avoid your program to have undefined behaviour. As a general rule of thumb, safe conversions are those conversions where a smaller type is converted to a larger type, whilst unsafe conversions are those where a long type gets **narrowed** to a shorter type. These are unsafe for various reasons, the most obvious being that part of the *large* value might not fit into the shorter type.

#### Safe Conversions - Widening Conversions (Promotion):

* char to int
* int to double
* bool to int
* float to double


#### Unsafe Conversions - Narrowing Conversions (Coercion):

* double to int
* double to char
* double to bool
* int to char
* int to bool
* char to bool


## Input/Output

In C++, I/O is based on **streams** of bytes flowing in and out of the program. The standard streams (and the ones you will use in the course) are **cin**, **cout** and **cerr**. The first is to handle keyboard input from the command line (STDIN), the second to handle output to the console (STDOUT) and the error stream (STDERR).

The <iostream> header file contains the cin, cout and cerr objects ready to use. An example of their use is the following:

```c++
#include <iostream>
#include <stdexcept>


int main()
{
   std::string name = "";
   const std::string ERROR = "error";

   std::cout << Enter your name << std::endl;
   std::cin >> name;

   if(name == ERROR) {
       throw std::runtime_error("ERROR--ABORTING");
   }

   try {

   std::cout << "Hello " << name << std::endl;

   }
   catch(const std::runtime_error& e) {
       std::cerr << e.what() << std::endl;
   }

   return 0;
}
```
This very simple (and stupid) program, asks the user for a name, reads it from standard input, and outputs *"Hello \<name\>"*, however if the name the user has input is "error", the program catches the exception and uses cerr to print the error message (See Module 3).

**NOTE:** The "std::endl" you see at the end of every "std::cout" instruction is there in order to print a new line. This is equivalent to printing a *newline character* (**\n**) as follows:

```c++

std::cout << "Hello, World\n";

```

* * *

### Intro To Compilers (EXTRA)

A compiler is a "*special*" program which translates source code written in higher-level languages (such as C++)
into lower-level language (such as, assembly, machine or object code) in order to create an **executable program**.
The compilation process of a C++ program involves three main steps:

1. Preprocessing
2. Compilation
3. Linking

#### Preprocessing

Preprocessor statements (*"Preprocessor Directives"*) in C++ (and C) source code, start with a **#** character (e.g., #include, #define, #ifdef, etc...). The preprocessor *"scans"* the source code before compiling it and looks for the **#** character, depending on the directive it acts accordingly.

The most common preprocessor directive in C++ is the #include statement, as it is needed to include the "iostream" file (and any other lib files) which contains the Input/Output objects (std::cin/std::cout) and their respective overloaded operators "\>\>" and "\<\<". The "iostream" file resides in the file system, and the preprocessor will essentially copy that file and paste it where the #include directive was placed in the source code.

The preprocessor eventually produces a single (intermediary) output file including some useful "notes" which give more information to the compiler, in order for the latter to make more sense of the code and therefore produce better and more detailed error messages.

#### Compilation

In the compilation stage, the files produced by the preprocessor are parsed and converted into *assembly code*. At this stage the **assembler** is called and the source code files get translated to *machine code* producing the actual binary file (**"object file"**).

The object files contain the compiled code in binary form, and can be put in special archives called static libraries, for easier reusing later on. At **this** stage, the *"compile-time errors"* such as syntax errors are reported.

#### Linking

The linker is the last entity involved in the compilation process and it is responsible for producing the final compilation output from all the object files created by the compiler.

This output file can either be an *executable* or a *shared/dynamic library*. It links all the object files by replacing the references to undefined symbols with the correct addresses. Each of these symbols can be defined in other object files or in libraries.

At this stage the most common errors are missing definitions or duplicate definitions. The former means that either the definitions don't exist (i.e. they are not written), or that the object files or libraries where they reside were not given to the linker. The latter is obvious: the same symbol was defined in two different object files or libraries.

* * *


# <a name="module2"></a>Module 2

> "Repetition is the mother of skill."

## Expressions

In C++ we can use all the arithmetic operators to make mathematical expressions. Operator precedence in C++ is very complex, however for the arithmetic operators, the classic "BIDMAS" order of operations applies. In order to override precedence, you can always use brackets. An example is:

```c++
constexpr int LENGTH = 5;
constexpr int WIDTH = 3;

const int area = LENGTH * WIDTH;
const int perimeter = (LENGTH + WIDTH) * 2;

```

As mentioned previously in *Module 1*, we can use constants for values we will not change at run-time. **constexpr** is a constant whose value **MUST** be known at compile time. **const** is constant whose value that can be known at run time as well, i.e., only one assignment can happen either at compile time or at run time.

## If Statements

If statements are used for "selection". Any code within the **scope** of the if statement is only run if the condition of the if statement is met. For example:

```c++

int value = 0;

std::cout << "Enter a number: " << std::endl;

std::cin >> value;

if(value < 0) {
  std::cout << "Your input is a negative number" << std::endl;
}
else if (value == 0) {
  std::cout << "Your input is 0" << std::endl;
}
else {
  std::cout << "Your input is a positive number" << std::endl;
}

```

The code snippet above, asks the user to input a number and based on the number outputs a string to standard out stating what kind of value was given by the user. Note how the last statement (**else**) does not need another condition testing if *value \> 0* because that is our only remaining option. The above example shows all three combinations of if statements (**if**, **else if** and **else**), The if statement however, can be used on its own without else and else if. The curly braces (*{}*) define a **scope** in C++. For example, if the input is "-1", the only code that is executed is that within the scope of the if statement having the condition "*value \< 0*" will be executed, i.e., "Your input is a negative number" will be printed to the console.


## Switch Statement

Switch statements are essentially like a big collection if "if-else if" statements, however they do offer a neater and more concise way of presenting the statements. Switch statements let you check an expression against several *constexpr values* called **cases**. Inside a switch block, execution starts with the matching constant and runs until the end of the switch statement, or until the next **break;**. There is a **default case** to "catch" everything else. For example:


```c++

constexpr char grade = 'D';

switch(grade) {
   case 'A' :
      std::cout << "Excellent!" << std::endl;
      break;
   case 'B' :
      std::cout << "Great!" << std::endl;
   case 'C' :
      std::cout << "Well done" << std::endl;
      break;
   case 'D' :
      std::cout << "You passed" << std::endl;
      break;
   case 'E' :
      std::cout << "Fail" << std::endl;
      break;
   default :
      std::cout << "Invalid grade" << std::endl;
}

```

## While Loops

Sometimes it may be desirable to repeat some code block multiple times. A while loop statement repeatedly executes a target statement as long as a given condition is true. There are *two* "flavours" of while loops. The classic **while** loop, and the **do-while** loop. the difference lies in when the condition is tested. In a while loop, the condition is tested for **before** executing the code. In a do-while loop, the code block is executed **first** and THEN, the condition is tested for truth. The thing to remember is that in a *do-while* loop, the code block is executed **at least once** no matter if the condition is met or not. This does NOT happen in a normal while loop. For example:

```c++
int value_while = 0;//test with TRUE condition
int value_do_while = 0;//test with TRUE condition

int test_while = 0;//test with FALSE condition
int test_do_while = 0;//test with FALSE condition


while(value_while < 10) {
    value_while++;
}

std::cout << "Value after while loop = " << value_while << std::endl; // = 10


do {
    value_do_while++;
}

while(value_do_while < 10);

std::cout << "Value after do-while loop = " << value_do_while << std::endl; // = 10

do {
    test_do_while++;
}

while(test_do_while > 1);

std::cout << "Value after do-while loop with FALSE condition = " << test_do_while << std::endl; // = 1



while(test_while > 1) {
    value_while++;
}

std::cout << "Value after while loop with FALSE condition = " << test_while << std::endl; // = 0

```

## For Loops

For loops are very useful to iterate over a sequence of numbers. As you will see in *Module 4*, you will need for loops a lot in order to traverse **arrays** and **vectors** in an easy manner. For example:


```c++

std::vector<int> dynamic_array;

for(int i = 0; i < 10; i++) {
  dynamic_array.push_back(i);//See Module 4
  std::cout << dynamic_array[i] << std::endl;
}

```

As you can see, within the for statement, there are 4 components. The *init* component (int i = 0), the *condition* (i < 10) which will be tested for truth value like in a while loop, the *increment* (i++), which unsurprisingly increments the **loop variable** (**i** is chosen by convention) and the *code block* which gets executed if the condition is true. What the code block above does is, populating a std::vector of type int, with the loop invariant and printing to STDOUT the value at each index.

A variant of the for loop in C++ is called a **Range-for loop** and can be very useful (and shorter to write) to traverse strings, arrays and vectors. The final outcome is the same as doing for loop in the *"traditional"* way! For example:

```c++

std::string name = "John";

for(char c : name) {
  std::cout << c << std::endl;
}

```

**NOTE:** It is *extremely* bad practice to change the value of your *loop variable* within the loop's code block. This can make your life extremely hard when **debugging** the code as it "breaks" the control flow of your program. The same goes for the **goto statement**, which is not covered in this course and should **NOT** be used.

**EXTRA:** Another important concept in C++ is **iterators** which are extremely useful (if not essential), when handling vectors (Module 4). Iterators can be used in for loops (and other control flow statements) in C++. The example above can be rewritten with iterators as follows:

```c++

std::vector<int> dynamic_array = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};

std::vector<int>::iterator it;

for(it = dynamic_array.begin(); it < dynamic_array.end(); it++) {
int& i = * it;
std::cout << i << std::endl;
}

```

The code above as of now might still seem very confusing for most of you, and this is why you are not supposed to understand this at this stage, and nor are you required to do so throughout this course, but it is here to show you that C++ is a very complex language that covers many topics in programming, and many things can be done in many different ways. :)


## Functions

When programming, it is **essential** for clarity to split logically blocks of code into different functions (and possibly different files). Functions are also useful to avoid the common paradigm of **spaghetti code**, which is code that is very hard to maintain, i.e., spaghetti code will eventually "break" when modifying certain parts of the code.

Functions can have **arguments/parameters** or not, however, as you will notice whilst working on your code, functions without any parameters will not be very useful. Imagine a mathematical function f(x) = y that takes as input x and generates y as an output. A function **declaration** is something like:

```c++

int square(int);

void log(std::string);

```

and is usually contained within a **header file** (which you are not required to use at this stage).

A function **definition** is something like:

```c++

int square(int a) {
  return (a * a);
}

void log(std::string name) {
  std::cout << name << std::endl;
}

```

As you can see, like variables, functions can have a type such as int or "*not*" having "type" void. Notice that I put "not" in quotes, because *void* is a valueless type and hence does **NOT** need a return value at the end of the function, even though it *technically* is a type as well.

**NOTE:** the **main** function is always of type *int*, and the return value is returned to the **Operating System** when the execution has ended. If everything goes well, **0** will be returned.


### Ternary Operator (EXTRA)

The Ternary operator is a very neat way to "compress" an if-else statement into a single line. Ternary operators can be nested just like if-else statements, however, if not used sparingly, they can be counterproductive and cause the code to be unclear at times. The ternary operator (? :) is used to return a value depending on a condition, e.g., *Condition ? X : Y* which means If Condition is true ? then it returns value X : otherwise value Y. An example of how to use ternary operators is as follows:

```c++

#include <iostream>


int min(int a, int b) {
    return ((a < b) ? a : b);
}

int main()
{
   int first_value = 0, second_value = 0;

   std::cin >> first_value >> second_value;

   int minimum_value = min(first_value, second_value);

   std::cout << minimum_value << std::endl;

   return 0;
}

```

As you can see, the "min" function is defined in just three lines, only one being the code block. If we hadn't used the ternary operator, that function would have been written as:


```c++

int min(int a, int b) {
  if(a < b) {
    return a;
  }
  else {
    return b;
  }
}

```

This is considerable longer. So, use ternary operators but do so **sparingly** to avoid overly messy code.

### Function Templates (EXTRA)

Function templates can be a very useful feature in C++ when declaring functions that need to adapt to accept parameters of different types. Imagine writing a log function which takes as a parameter a variable, and logs it to the console for debugging or whatever other reason. It is fairly simple to use template functions, and they can save you a lot of typing on top of making your code much neater. An example of a log() template function is:


```c++

#include <iostream>


template <typename T> void log(T value) {
    std::cout << "The value is: " << value << std::endl;
}

int main()
{

    int a = 42;
    std::string name = "John";
    char grade = 'A';

    log <int> (a); //preferred way of calling template function.
    log <std::string> (name);
    log(grade);


   return 0;
}

```
So, to declare a template function we need to add (unsurprisingly), the keyword *template*, followed by angle brackets containing a *typename definition* which I called "T", but just like a variable can be named in any (sensible) way. The rest of the declaration is just as we would expect normally.

When a template function is called, we have two possibilities, either calling it just as a normal function, log(grade), or, preferably by passing the type in the angle brackets as an argument, log <std::string> (name). The second is preferred, because it makes clear the fact that "log()" is a template function and can be used as such.

From the point of view of the compiler, templates are not normal functions or classes. They are compiled on demand, meaning that the code of a template function is not compiled until an instantiation with specific template arguments is required. At that moment, when an instantiation is required, the compiler generates a function specifically for those arguments from the template.

* * *

# <a name="module3"></a>Module 3

>"Houston, we've had a problem here"

## Compile Time Errors



# <a name="module4"></a>Module 4

# <a name="module5"></a>Module 5

# <a name="module6"></a>Module 6

# <a name="module7"></a>Module 7

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.


#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.


### There's a horizontal rule below this.

* * *



### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://assets-cdn.github.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
