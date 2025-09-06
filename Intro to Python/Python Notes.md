**Variable**  
- A name that refers to a value.

**Statement**
- A **statement** is an instruction that the Python interpreter can execute.

**Expression**
- An **expression** is a combination of literals, variable names, operators, and calls to functions. Expressions need to be *evaluated*. The result of evaluating an expression is a _value_ or _object_.

**Functions**
- Like methods in java

```python
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
```python
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
```python
x = 15

if x % 2 == 0:
    print(x, "is even")
else:
    print(x, "is odd")
```

**Chained condition**
- Includes an elif condition
```python
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
```python
total  = 0
n = 10
a_number = 1
while a_number <= n:
    total = total + a_number
    a_number = a_number + 1
    print(total)
```

**Loops with arrays / lists**

*Method 1*
```python
fruits = ["apple", "orange", "banana", "cherry"]
for fruit in fruits:     # by item in list
    print(fruit)
```

*Method 2*
```python
print("This will execute first")

for i in range(3):
    print("This line will execute three times")
    print("This line will also execute three times")

print("Now we are outside of the for loop!")
```

*Method* 3
```python
fruits = ['apple', 'pear', 'apricot', 'cherry', 'peach']
for n in range(len(fruits)):
    print(n, fruits[n])
```

**Iterate and accumulate a list**
```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
accum = 0
for w in nums:
    accum = accum + w
print(accum)
```

**Tuples**

`julia = ("Julia", "Roberts", 1967, "Duplicity", 2009, "Actress", "Atlanta, Georgia")`

A **tuple**, like a list, is a sequence of items of any type. The printed representation of a tuple is a comma-separated sequence of values, enclosed in parentheses. In other words, the representation is just like lists, except with parentheses () instead of square brackets [].

The key difference between lists and tuples is that a tuple is immutable, meaning that its contents can’t be changed after the tuple is created

###### **Slicing**

We can easily slice off the parts we want and concatenate them with the new tuple.

```python
julia = julia[:3] + ("Eat Pray Love", 2010) + julia[5:]
print(julia)
```

`('Julia', 'Roberts', 1967, 'Eat Pray Love', 2010, 'Actress', 'Atlanta, Georgia')`

**List slice**
Slices out the required parts 
```python
a_list = ['a', 'b', 'c', 'd', 'e', 'f']
print(a_list[1:3])
```

`['b', 'c']`

**String slice with comma**

```python
singers = "Peter, Paul, and Mary"
print(singers[0:5])
```

**Slice list**
Slicing a list creates a new list — it’s **not the same object**.
```python
b = a[:] 
```

**String concatenation**

```python
fruit = ["apple","orange","banana","cherry"]
print([1,2] + [3,4])
print(fruit+[6,7,8,9])

print([0] * 4)
```

`[1, 2, 3, 4]`
`['apple', 'orange', 'banana', 'cherry', 6, 7, 8, 9]`
`[0, 0, 0, 0]`

**Index() function**

``` python
music = "Pull out your music and dancing can begin"
bio = ["Metatarsal", "Metatarsal", "Fibula", [], "Tibia", "Tibia", 43, "Femur", "Occipital", "Metatarsal"]

print(music.index("m"))
print(music.index("your"))

print(bio.index("Metatarsal"))
print(bio.index("Tibia"))
print(bio.index([]))
print(bio.index(43))
```

```js
14
9
0
4
3
6
```

**Split function()**

``` python
song = "The rain in Spain..."
wds = song.split() #split using space, we can add , or any value
print(wds) 
```

`['The', 'rain', 'in', 'Spain...']`

```python
wds = ["red", "blue", "green"]
glue = ';'
s = glue.join(wds)
print(s)
print(wds)

print("***".join(wds))
print("".join(wds))
```

`red;blue;green`
`['red', 'blue', 'green']`
`red***blue***green`
`redbluegreen`

**Semantic Error**
- This will produce the wrong answer because the programmer implemented the solution incorrectly. This is a semantic error.

**Functions**
```python
def hello():
    """This function says hello and greets you""" #docstrings
    print("Hello")
    print("Glad to meet you")
```

**Docstrings  
  
If the first thing after the function header is a string (some tools insist that it must be a triple-quoted string), it is called a docstring and gets special treatment in Python and in some of the programming tools.

**Type Annotations**

```python
def duplicate(msg: str) -> str:
    """Returns a string containing two copies of `msg`"""

    return msg + msg

result = duplicate('Hello')
print(result)
```

This process of breaking a problem into smaller subproblems is called **functional decomposition** using functions. 

##### **Dictionary (Key-Value Pairs)**
- A collection of key-value pairs that maps from keys to values. The keys can be any immutable type, and the values can be any type

```python
eng2sp = {} #empty dict
eng2sp['one'] = 'uno' # {one : uno}
eng2sp['two'] = 'dos' # {two : dos}
eng2sp['three'] = 'tres' # {three : tres}
print(eng2sp) 

#{'three': 'tres', 'one': 'uno', 'two': 'dos'}
```

**Dictionary operations**

```python
inventory = {'apples': 430, 'bananas': 312, 'oranges': 525, 'pears': 217}
del inventory['pears']
inventory['apples'] = 0

#apples 0
#bananas 312
#oranges 525
```

Iteration over Dictionary

```python
inventory = {'apples': 430, 'bananas': 312, 'pears': 217, 'oranges': 525}

for akey in inventory.keys():   
    print("Got key", akey, "which maps to value", inventory[akey])

ks = list(inventory.keys())       # Make a list of all of the keys
print(ks)
print(ks[0]) 


# Got key apples which maps to value 430
# Got key bananas which maps to value 312
# Got key pears which maps to value 217
# Got key oranges which maps to value 525
# ['apples', 'bananas', 'pears', 'oranges']
# apples 
```

**Items()**
- The `items` method returns a collection of tuples containing each key and its associated value. 

```python
inventory = {'apples': 430, 'bananas': 312, 'oranges': 525, 'pears': 217}
print(list(inventory.items()))
	for k, v in inventory.items():
		print("Got", k, "that maps to", v)

#[('apples', 430), ('bananas', 312), ('oranges', 525), ('pears', 217)]
#Got apples that maps to 430
#Got bananas that maps to 312
#Got oranges that maps to 525
#Got pears that maps to 217
```

**Values()**
- The `values` method returns a collection of the values in the dictionary.

```python
inventory = {'apples': 430, 'bananas': 312, 'oranges': 525, 'pears': 217}
print(list(inventory.values()))
for v in inventory.values():
    print("Got", v)

#[430, 312, 525, 217]
#Got 430
#Got 312
#Got 525
#Got 217
```

**Get()**
- `get` retrieves the value associated with a key, similar to the `[]` operator. The important difference is that `get` will not cause a runtime error if the key is not present. It will instead return the value `None`
```python
inventory = {'apples': 430, 'bananas': 312, 'oranges': 525, 'pears': 217}

print(inventory.get("apples"))
print(inventory.get("cherries"))

print(inventory.get("cherries",0))

#430
#None
#0
```

**List Methods**
![[Pasted image 20250907014524.png]]