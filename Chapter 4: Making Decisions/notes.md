# Making Decisions

### Relational Operators
----------
* Used to compare numbers to determine relative order
* Relational Operators:
    - ">" Greater than
    - "<" Less than 
    - ">=" Greater than or equal to
    - "<=" Less than or equal to
    - "==" Equal to
    - "!=" Not equal to
#### Relational Expressions
* Integer data types can be interpreted as bool
    * 0 is interpreted as false
    * Non-zero values are true

* bool is also associated with an integer
    * false is always zero
    * true is not necessarily equal to 1

### The if statement
----------
* Allows statements to be conditionally executed or skipped over
* Models the way we mentally evaluate situations:
    * "If it is raining, take an umbrella"
    * "If it is cold outside, take a coat"

![flowchart](/home/ash/Pictures/Screenshots/240206_18h02m04s_screenshot.png)

#### General format
```cpp
if(condition){
    statement;
}
```
* Always brace the bodies of your control structures even if it's just a single line.

### The if/else Statement
----------
* Provides two possible paths of execution
* Performs one statement or block if the expression is true, otherwise performs an alternative block of code

#### General Format

```cpp
if(condition){
    statement; // or block
}else{
    statement2; // or block
}
```

![flowchart_tf](/home/ash/Pictures/Screenshots/240206_18h07m44s_screenshot.png)

### Nested if statements
----------

* An if statement that is nested inside another if statement
* Nested if statements can be used to test more than one condition

![flowchart_nested](/home/ash/Pictures/Screenshots/240206_18h09m18s_screenshot.png)

### The if/else if sequence
----------

```cpp
if(condition1){
    statement1;
}
else if(condition2){
    statement2;
}
else if(conditionN){
    statementN;
}
```
![flowchartElseIf](/home/ash/Pictures/Screenshots/240206_18h12m27s_screenshot.png)

### Logical Operators
----------
* Used to create relational expressions from other relational expressions
* Operators, meaning and explanation:

| &&    | AND    | New relational expression is true if both expressions are true    |
|---------------- | --------------- | --------------- |
| "ll "    | OR    | New relational expression is true if either expression is true    |
| !    | NOT    | Reverses the value of an expression - true expression becomes false, and false becomes true    |

* ! has highest precedence, followed by &&, then ||
* If the value of an expression can be determined by evaluating just the sub-expression on left side of a logical operator, then the sub expression on the right side will not be evaluated (short cirtcuit evaluation)

### Checking Numeric Ranges with Logical Operators
----------
* Used to test to see if a value falls inside a range:
```cpp
if(grade >= 0 && grade <= 100)
    cout << "Valid grade";
```
* Cannot use mathematical notation:
`if(0 <= grade <= 100) // Doesn't work` 

### Validating User Input
----------
* Input validation: Inspecting input data to determine whether it is acceptable
* Bad output will be produced from bad input
* Can perform various test
    - Range
    - Reasonableness
    - Valid menu choice
    - Divide by zero

### Comparing Characters and strings
----------
* Characters are compared using their ASCII values

* 'A' < 'B'
    
