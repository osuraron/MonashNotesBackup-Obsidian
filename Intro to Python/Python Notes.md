**Variable**  
- A name that refers to a value.

**Statement**
- A **statement** is an instruction that the Python interpreter can execute.

**Expression**
- An **expression** is a combination of literals, variable names, operators, and calls to functions. Expressions need to be *evaluated*. The result of evaluating an expression is a _value_ or _object_.

**Functions**
- Like methods in java

```cpp
def square(x):
   return x * x
```

**Order of Operations**
- _Parentheses_ have the highest precedence and can be used to force an expression to evaluate in the order you want.

- _Exponentiation_ has the next highest precedence, so `2**1+1` is 3 and not 4, and `3*1**3` is 3 and not 27. 

- _Multiplication and both division_ operators have the same precedence, which is higher than addition and subtraction, which also have the same precedence. So `2*3-1` yields 5 rather than 4

- Operators with the **_same_** precedence are evaluated from ***left-to-right*.**** In algebra we say they are _left-associative_. So in the expression `6-3+2`, the subtraction happens first, yielding 3. We then add 2 to get the result 5.

![[Pasted image 20250817200636.png]]

**User input and printing**
```cpp
n = input("Please enter your name: ")
print("Hello", n)
print(f"Hello {n}") //formated way
```

**List**
A **list** is a sequential collection of Python data values, where each value is identified by an index. The values that make up a list are called its **elements**.

`[10, 20, 30, 40]`
`["spam", "bungee", "swallow"]`

**In and Not In**
The `in` operator tests if one string is a substring of another:
The `not in` operator returns the logical opposite result of `in`.

`print('p' in 'apple')`
`print('x' not in 'apple')`

**Unary selection**  
- A selection statement in which there is only an “if” statement and the “else” statement is omitted entirely. In an unary selection, the statements are only executed if the condition evaluates to true, otherwise the program continues to the body following the if statement.

**Conditional statement** / (Selection Statements)
- A statement that controls the flow of execution depending on some condition. In Python the keywords `if`, `elif`, and `else` are used for conditional statements.
- 
```cpp
x = 15

if x % 2 == 0:
    print(x, "is even")
else:
    print(x, "is odd")
```

**Chained condition**
- Includes an elif condition
```cpp
x = 10
y = 10

if x < y:
    print("x is less than y")
elif x > y:
    print("x is greater than y")
else:
    print("x and y must be equal")
```

**While Loops**
```cpp
total  = 0
n = 10
a_number = 1
while a_number <= n:
    total = total + a_number
    a_number = a_number + 1
    print(total)
```

