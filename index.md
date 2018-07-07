---
layout: default
---

[Link to another page](./another-page.html).

The Sections of this page marked as *(EXTRA)* are **NOT** essential for passing the course, however they do give a greater insight on the C++ language, and might help you in future courses. Students who are not interested in going the "extra mile" can safely ignore these sections.

# Module 1

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


## Operators

In C++, there are many built-in operators and are divided into 6 main categories:

1. Arithmetic Operators (+, -, \*, /, %, ++, --)
2. Relational Operators (==, !=, <, >, <=, >=)
3. Bitwise Operators (&, |, ^, ~, <<, >>)
4. Logical Operators (&&, ||, !)
5. Assignment Operators (=, +=, -=, \*=, /=, %=, &=, <<=, >>=, |=, ^=)
6. Misc Operators (sizeof, ., ->, &, \*, Cast, *Ternary*)

The Arithmetic operators, are fairly straight-forward and most, behave as expected. The only two operators that might need a brief explanation are the **Modulo** (**%**) operator, which is a binary operator (takes two "arguments") that returns the remainder of the division operation on two numbers. E.g., 20 % 3 evaluates to 2. The **increment/decrement** (**++/--**) are unary operators, and can be used as a *prefix* OR *suffix*. If these operators are placed *before* the variable, the variable is incremented/decremented and THEN use the incremented/decremented value. For example:

```c++
int a = 20;
int b = 3;

int remainder = (a % b);// = 2

a++; //a = 21
--b; //b = 2

```

The most common operators are contained in the following table:

| Operator        | Name            | Short Description|
|:----------------|:----------------|:-----------------|
| unsigned char   | 1 Byte          | 0 ~ 255          |
| signed char     | 1 Byte          | -147 ~ 147       |
| unsigned int    | 4 Bytes         | 0 ~ 4294967295   |
| signed int      | 4 Bytes         | -2147483648 ~ 2147483647 |
| short int       | 2 Bytes         | -32768 ~ 32767   |
| long int        | 4 Bytes         | -2147483648 ~ 2147483647 |
| float           | 4 Bytes         | +/- 3.4e +/- 38 (~7 digits) |
| double          | 8 Bytes         | +/- 1.7e +/- 308 (~15 digits) |



### Intro To Compilers (EXTRA)

A compiler is a "*special*" program which translates source code written in higher-level languages (such as C++)
into lower-level language (such as, assembly, machine or object code) in order to create an **executable program**.
The compilation process of a C++ program involves three main steps:

1. Preprocessing
2. Compilation
3. Linking

#### Preprocessing

Preprocessor statements (*"Preprocessor Directives"*) in C++ (and C) source code, start with a **#** character (e.g., #include, #define, #ifdef, etc...). The preprocessor *"scans"* the source code before compiling it and looks for the **#** character, depending on the directive it acts accordingly.

The most common preprocessor directive in C++ is the #include statement, as it is needed to include the "iostream" file (and any other lib files) which contains the Input/Output objects (std::cin/std::cout) and their respective overloaded operators ">>" and "<<". The "iostream" file resides in the file system, and the preprocessor will essentially copy that file and paste it where the #include directive was placed in the source code.

The preprocessor eventually produces a single (intermediary) output file including some useful "notes" which give more information to the compiler, in order for the latter to make more sense of the code and therefore produce better and more detailed error messages.

#### Compilation

In the compilation stage, the files produced by the preprocessor are parsed and converted into *assembly code*. At this stage the **assembler** is called and the source code files get translated to *machine code* producing the actual binary file (**"object file"**).

The object files contain the compiled code in binary form, and can be put in special archives called static libraries, for easier reusing later on. At **this** stage, the *"compile-time errors"* such as syntax errors are reported.

#### Linking

The linker is the last entity involved in the compilation process and it is responsible for producing the final compilation output from all the object files created by the compiler.

This output file can either be an *executable* or a *shared/dynamic library*. It links all the object files by replacing the references to undefined symbols with the correct addresses. Each of these symbols can be defined in other object files or in libraries.

At this stage the most common errors are missing definitions or duplicate definitions. The former means that either the definitions don't exist (i.e. they are not written), or that the object files or libraries where they reside were not given to the linker. The latter is obvious: the same symbol was defined in two different object files or libraries.




# Module 2

# Module 3

# Module 4

# Module 5

# Module 6

# Module 7

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

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


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
