# Chapter 3: Expressions and Interactivity

### The cin object 
----------
* Standard input object
* Like cout, requires iostream
* Used to read input from keyboard
* Information retrieved from cin with >>
* input is stored in one or more variables

* If an int is expected and you enter a floating-point value, bad things will happen...

Console input is fragile. It was intended to read data from files, the data format being known in advance. It was never meant for unpredictable input.

### Mathematical Expressions
----------
* Can create complex expressions using multiple mathematical operatiors
* An expression can be a literal, a var, or a mathematical combination of consts and vars
* Can be used in assignment, cout, and other statements.

`circumference = 2 * PI * radius;` 

#### Order of Operations
In an expression with more than one operator, evaluate in this order:
- "-" (unary negation), in order, left to right
- "*" / %, in order, left to right
- "*" -, in order, left to right

#### Associativity of Operators
- "-" (unary negation), associates right to left
- "*" /, %, +, - associate right to left
- parentheses() can be used to override the order of operations

#### Algebraic Expressions
- Multiplication requires an operator:
    Area = lw is written as `Area = l * w;`
- There is no exponentiation operator:
    Area=s<sup>2 is written as `Area = pow(s, 2);` 
- Parentheses may be needed to maintain order of operations

### Type Conversion
----------
- Operations are performed between operands of the same type.
- If not of the same type, C++ will convert one to be the type of the other
- This can impact the results of calculations.

#### Type Coercion
- Type Coercion: automatic conversion of an operand to another data type
- Promotion: convert to a higher type
    - Happens automatically (and quietly) in most programming languages
- Demotion: convert to a lower type
    - Automatic (and quiet!) in C and C++; generates an error in most newer languages.

#### Coercion Rules
1) Char is automatically promoted to int and int is promoted to double.
2) When operating on values of different data types, the lower one is promoted to the type of the higher one.
3) When using the = operator, the type of expression on right will be converted to type of variable on left.

### Type Casting
----------
- Used for manual data type conversion
- Useful for safely truncating floating-point types for storage in an integer location
```CPP
int i;
double m;
 *
 *
i = static_casket<int>(m)
```
- You can also use "old style" casting:
```cpp
int i;
double m;
 *
 *
i = (int) m;
```
- That line without the (int) will generate an error in most newer languages like Java.
- Can be used to see int value of a char variable:
```cpp
char ch = 'C';
cout << ch << " is "
    << static_cast<int>(ch);
```
- You can also use "old style" casting...
```CPP
char ch = 'C';
cout << ch << " is " << (int) ch;
```
- We will always use "old style" ins this class.

### Multiple Assignment and Combined Assignment
----------
- The = can be used to assign a value to multiple variables:
    `x = y = z = 5;` 
- Value of = is the value that is assigned, always going to be assigned = assignment

#### Combined Assignment
- Look at the following statement
    `sum = sum + 1;`
    this adds 1 to the variable sum.
- The combined assignment operators provide a shorthand for these types of statements.
- The statement: 
`sum = sum + 1;`
is equivalent to `sum += 1;`

### Formatting Output
----------
- Can control how output displays for numeric, string data 
    - size
    - position
    - number of digits
- This does require the iomanip header file

#### Stream Manipulators
- Used to control how an output field is displayed
- Some affect just the next value displayed:
    - setw(x): print in a field at least x spaces wid. Use more spaces if field is not wide enough
- Some affect values until changed again:
    - fixed: use decimal notation for floating-point values
    - setprecision(x): when used with fixed print floating-point value using x digits after the decimal. Without fixed, print floating-point value using x significant digits
    - showpoint: always print decimal for floating-point values

- If you need any one of these use all three!!!

### Working with Characters and string Objects
----------
- Using cin with the >> operator to input strings can cause problems:
- It passes over and ignores any leading *whitespace characters (spaces, tabs, or line breaks)*
- To work around this problem, you can use the function getline() in C++

- To read a single character:
- Use cin:
```cpp
char ch;
cout << "Strike any key to continue";
cin >> ch;
```
- Use cin.get()
    `cin.get(ch);`
    will read the next character entered even whitespace
- Mixing cin >> and cin.get() or getline() in the same program can cause input errors that are hard to detect
- To skip over unneeded characters that are still in the keyboard buffer, use cin.ignore() before any getline or get that follows a cin

#### **string** Member Functions and Operators  
- To find the length of a string:
```cpp
string state = "Texas";
int size = state.length();
```
- To concatenate (join) multiple strings:
```cpp
greeting2 = greeting1 + name1;
greeting1 = greeting1 + name2;
```
- Or use the += operator:
`greeting1 += name2;`

### More Mathematical Library Functions
----------
- Requires the cmath header file
- Many accept double as input and return double; others are int functions
- Commonly used functions:
    - sin(Sine)
    - cos(Cosine)
    - tan(Tangent)
    - sqrt(Square Root)
    - log(Natural (e)log)
    - abs(Absolute value)

#### Pseudorandom numbers
- rand(): returns a pseudorandom integer between 0 and the largest int the compute holds.
- We often use the % operator with pseudorandom numbers to get the range of values desired `rand();`

#### Seeding the RNG
- srand(x): initializes random number generator with unsigned int x
- We can "seed" the RNG with a "puzzle number" to recreate the same game
- We seed the RNG with the current time to ensure that we get a different game with even run
`srand((unsigned)time(0));`

- Initializes RNG with the current system time, to the nearest second
- Requires the ctime library
- This line appears only once in the program in the main function
