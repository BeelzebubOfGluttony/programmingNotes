# Chapter 2: Intro to C++

### Program 1-1
```cpp
#include <iostream>
using namespace std;

int main()
{
    double hours, rate, pay;

    cout << "How many hours did you work?";
    cin >> hours;

    cout << "How much do you get paid per hour?";
    cin >> rate;

    pay = hours * rate;
    
    cout << "You have earned $" << pay << endl;
    return 0;
}
```

### Escape sequences
----------
* Escape sequences are used to create characters that can't be entered from the keyboard, or for enclosure in string litereals

| Sequence   | What it means    |
|--------------- | --------------- |
| \ "   | double quote
| \t   | tab   |
| \ \   | backslash   |

### The #include directive
----------
* Inserts the contents of another file into the program
* This is a preprocessor directive, not part of C++ lang
* #include lines are not seen by the compiler
* Do not place a semicolon at end of #include line
* Primary use is to import libraries into a program

### Identifiers
----------
* An identifier is a programmer-defined name for some part of a program: variables, constants, functions, objects, and so on.

#### Identifier rules
----------
* The first character of an identifier must be an alphabetic character or an underscore.
* Subsequent characters may be alphabetic characters, numbers, or underscore characters.
* Upper and lower case characters are distinct.

#### Identifier guidelines
----------
A variables name should represent the purpose of the variable 

`items_ordered // old way`

`itemsOrdered // new way` 

Objects tend to use a uppercase and ordinary variables tend to use lower case.

When it comes to temporary variables it is okay to use single character names as the variable will usually be discarded.

We keep constants as full UPPER CASE names to represent they never change. We define this with the identifier `const` 

## Data types

### Integer data type
* Integer variables can hold signed whole numbers
* Can be signed or unsigned
* The sizes of the integer data type varies by computer

### Char data type
* Used to hold characters and really small integer values
* Always one byte of memory in C and C++
* Numeric value of character from the character set is stored in memory
#### Char Literals
----------
* Must be enclosed in single quotes
* These chars are really just disguised integers:
```CPP
ch = 'A' + 1; // changes the value of ch to B
```

### String class 
* A string is just a sequence of characters.
* To use a string in our program we include `#include <string>` 
* Strings are a really simple data type in the C family, not much more to talk about.

### Floating-point data types
* The floating point data types are:
> float (usually 4 bytes)

> double (usually 8 bytes)

> long double (usually 8 bytes as well)

* They can hold real numbers such as:

| Real Numbers  |
|-------------- |
| 12.45    |
| -3.8    |
| 1.23 x 10<sup>3    |

* Stored in a similar form to scientific notation

### Bool data type
* Represents values that are true or false
* Used to control loops and branches
* Since C did not have a bool data type, integers can represent bool values
    - zero is false, non-zero is true.
