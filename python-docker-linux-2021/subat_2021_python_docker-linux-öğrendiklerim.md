# Day-1
Input
Prints a string into the console,
and asks the user for a string input.
```python
input("What's your name")
```

# Day-2
Variables
A variable give a name to a piece of data.
Like a box with a label, it tells you what's
inside the box.

```python
my_name = "Angela"
my_age = 12
```

# Day-3
The += Operator
This is a convient way of saying: "take the
previous value and add to it.
```python
my_age = 12
my_age += 4
#my_age is now 16
```

# Day-4
Floating Point Numbers
Floats are numbers with decimal places.
When you do a calculation that results in
a fraction e.g. 4 ÷ 3 the result will always be
a floating point number.
```python
my_float = 3.14159
```
# Day-5
String Concatenation
You can add strings to string to create
a new string. This is called concatenation.
It results in a new string.
```python
"Hello" + "Angela"
#becomes "HelloAngela"
```
# Day-6
Escaping a String
Because the double quote is special, it
denotes a string, if you want to use it in
a string, you need to escape it with a "\"
```python
speech = "She said: \"Hi\""
print(speech)
#prints: She said: "Hi"
```

# Day-7
F-Strings
You can insert a variable into a string
using f-strings.
The syntax is simple, just insert the variable
in-between a set of curly braces {}.
```python
days = 365
print(f"There are {days} in a year")
```

# Day-8
Converting Data Types
You can convert a variable from 1 data
type to another. 
Converting to float: float() 
Converting to int: int() 
Converting to string: str()
```python
n = 354
new_n = float(n)
print(new_n) #result 354.0
```

# Day-9
Checking Data Types
You can use the type() function
to check what is the data type of a
particular variable.
```python
n = 3.14159
type(n) #result float
```

# Day-10
Name Error
This happens when there is a variable
with a name that the computer
does not recognise. It's usually because
you've misspelt the name of a variable
you created earlier.
Note: variable names are case sensitive!
```python
my_number = 4
my_Number + 2
Traceback (most recent call
last): File "<stdin>", line 1,
NameError: name 'my_Number'
is not defined
```

# Day-11
Functions
This is the basic syntax for a function in
Python. It allows you to give a set of
instructions a name, so you can trigger it
multiple times without having to re-write
or copy-paste it. The contents of the function
must be indented to signal that it's inside.
```python
def my_function():
print("Hello")
name = input("Your name:")
print("Hello")
```
# Day-12
Keyword Arguments
When calling a function, you can provide
a keyword argument or simply just the
value.
Using a keyword argument means that
you don't have to follow any order
when providing the inputs.
```python
def divide(n1, n2):
result = n1 / n2
#Option 1:
divide(10, 5)
#Option 2:
divide(n2=5, n1=10)
```
# Day-13
Elif
In addition to the initial If statement
condition, you can add extra conditions to
test if the first condition is false.
Once an elif condition is true, the rest of
the elif conditions are no longer checked
and are skipped.
```python
weather = "sunny"
if weather == "rain":
print("bring umbrella")
elif weather == "sunny":
print("bring sunglasses")
elif weather == "snow":
print("bring gloves")
```
# Day-14
and
This expects both conditions either side
of the and to be true.
```python
s = 58
if s < 60 and s > 50:
print("Your grade is C")
```
# Day-15
or
This expects either of the conditions either
side of the or to be true. Basically, both
conditions cannot be false.
```python
age = 12
if age < 16 or age > 200:
print("Can't drive")
```
# Day-16
not
This will flip the original result of the
condition. e.g. if it was true then it's now
false.
```python
if not 3 > 1:
print("something")
#Will not be printed.
```

# Day-17
comparison operators
These mathematical comparison operators
allow you to refine your conditional checks.
```python
> Greater than
< Lesser than
>= Greater than or equal to
<= Lesser than or equal to
== Is equal to
!= Is not equal to
```

# Day-18