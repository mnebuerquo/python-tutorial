.center[![import antigravity](https://imgs.xkcd.com/comics/python.png)]
.center[[XKCD #353: Python](https://xkcd.com/353/)]

---

# Sherman's One-Hour Python Tutorial

Let's learn some basics of python in 60 minutes.

We'll assume you already have python 2.7 installed. The code here should
work in 3.x as well.

???
Does Sherman really know python?

---

# Running Python Interactively

The `python` command starts the python interpreter.

```bash
bash$ python
```

You will see the following prompt:

.hljs[
```
Python 2.7.12 (default, Oct 11 2016, 05:24:00)
[GCC 4.2.1 Compatible Apple LLVM 8.0.0 (clang-800.0.38)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
]

--

Now try telling python to do something:
```python
>>> print("hello world")
hello world
>>>
```

---

# Running a Python Script

This is a simple python script, which we'll save as tut1.py:

```python
#!/usr/bin/python
print("hello world")
```

--

Make the script executable:

```bash
bash$ chmod +x tut1.py
bash$
```

--

Run the script from the command prompt:

```bash
bash$ ./tut1.py
hello world
bash$
```

--

You have just written and executed your first python program!

---

# Variables in Python

You create a variable just by assigning to it. No var or other
instantiation keywords. No declaration, just assign.

```python
x = 7
y = "foo"
pi = 3.14159265
```

---

# Numbers in Python

Integers:
```python
x = 10
y = 3
print(x/y) # prints 3
           # (notice that integer division gives you an integer)
```

--

Floating Point:
```python
x = 3.14159265
y = 7
print(x/y) # prints 0.44879895000000003
```

---

# Control Flow

Blocks are defined in python by indenting the code.

The `if` statement executes the indented code block if the condition
evaluates to `True`:
```python
if condition:
    statement
elif condition:
    statement
else:
    statement
```

-- 

Another form of if is the ternary operator:
```python
y = 7
x = 5 if y>1 else 10 # x is now equal to 5
```

---

# Loops

The for loop iterates over a sequence:
```python
for name in [ "bob", "sam", "ben", "sue", "bev" ]:
    print(name)
```

--

You can use the range function to use a numeric counter:
```python
for i in range(10):
    print(i) # prints 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
```

--

The while loop iterates as long as a condition is true:
```python
i = 0
while i < 10:
    print(i)
    i = i+1
```

---

# Exiting a Loop

The `continue` statement skips to the next iteration of the loop and
continues looping:
```python
for i in range(10):
    if i == 3:
        continue
    print(i) # prints 0 1 2 4 5 6 7 8 9
```

--

The `break` statement skips out of the loop without executing any more
iterations.
```python
for i in range(10):
    if i == 3:
        break
    print(i) # prints 0 1 2
```

---

# Else

The `else` is not just used after `if`, but can follow a loop:
```python
for i in range(10):
    pass # this statement does nothing! use it as a placeholder
else:
    print("else")
```

--

The `else` block is only executed after the loop condition evaluates
as `False`, but not following a `break`:
```python
for i in range(10):
    if i == 3:
        break
else:
    print("else")   # this line is skipped

print("done")       # prints "done"
```

---

# Sequence Types

There are six sequence types in python: str, unicode, list, tuple, buffer, xrange.
We are going to talk about str, list, tuple.

--

Access elements of a sequence (such as a string) using brackets. The indexes
start with zero:
```python
x = "bar"
print(x[0]) # b
print(x[1]) # a
print(x[2]) # r
```

This may look familiar like arrays in other languages.

--

Strings are written using double quotes.
```python
x = "this is a test"
print( len(x) ) # prints 14
print( x[10] )  # prints t
```

---

# Lists and Tuples

Lists are constructed with brackets and every element should be the same
type. Lists can be changed and appened (mutable).
```python
mylist = [ "foo", "bar", "baz", "wow" ]
mylist[4] = "new"
print( mylist[4] ) # prints "new"
```

--

Tuples are created with parentheses. They can not be appended nor can elements
be replaced (immutable).  You would have to create a new tuple with different
elements instead.
```python
mytuple = (1, "foo", 3.14159265)
print( mytuple[1] ) # prints "foo"
mytuple[1] = "bar" # TypeError: 'tuple' object does not support item assignment
```

---

# Slices

```python
seq = [ "apple", "banana", "pear", "grape", "plum" ]
```

Slice `seq[ start: stop ]` returns a slice from the sequence, where
`start` is the first element in the slice, and `stop` is the element
after the slice.
```python
seq[1:3] # ['banana', 'pear']
```

--

Negative indexes count backwards from the end of the list. This works for
indexing single elements or slices:
```python
seq[-1]   # 'plum'
seq[1:-1] # ['banana', 'pear', 'grape']
seq[-3:3] # ['pear']
seq[-1:1] # []
```

--

You may omit either index in the slice to read from the start or to the end
of the list:
```python
seq[2:]  # ['pear', 'grape', 'plum']
seq[:3]  # ['apple', 'banana', 'pear']
seq[-2:] # ['grape', 'plum']
```

---

# Dictionaries

A dictionary maps keys to values. It is an unordered collection of key/value
pairs.
```python
d = { "foo": 37, "bar": 99, "baz": 42, "woo": 0 }
```

--

Access a key using bracket notation. You can add new keys this way too:
```python
d["foo"] # 37
d["what"] = 45
```

--

Remove a key using `del` operator:
```python
del d["bar"]
```

--

Use the `in` operator to check if a key exists:
```python
"foo" in d # True
"noo" in d # False
```

---

# Comprehensions

A list comprehension is a construct that generates a new list by
transforming a list.

The syntax: `[ expression for item in list if conditional ]`

```python
[x+1 for x in range(10) if x % 2 == 0] # [ 1, 3, 5, 7, 9 ]
```

---

# Functions

Define a function using `def`. Returning a value works similarly to other
languages:
```python
def cube( x ):
    return x * x * x
```

---

# Function vs Global Scope

Variables in a function are assumed to be local unless marked as global:
```python
glob = 0
def doSomething( x ):
    global glob
    glob += x
    print(glob)
```

--

Global variables are visible within a function but assignment creates a new
local which shadows the global.
```python
meaning_of_life = 42
def life(x):
	if x == meaning_of_life:
		return True
	else:
		return False
life(39) # false
life(42) # true
```

---

# Function Arguments

Function arguments can have default values. The arguments are positional, so
those with defaults must be specified last in the argument list:
```python
def myfunc( x, y=8, z=5 ):
    print(x, y, z)

myfunc( 1, 2 ) # prints (1, 2, 5)
```

--

When you call a function you can specify arguments by name:
```python
myfunc(7, z=9) # prints (7, 8, 9)
```

--

You can use `*args` and `**kwargs` to capture arguments without specifying
them in advance:
```python
def my_function(**kwargs):
    print str(kwargs)

my_function(a=12, b="abc") # {'a': 12, 'b': 'abc'}
```

---

# Lambda Forms

You can create an anonymous function in python using lambda:
```python
g = lambda x: x**2

g(8) # 64
```

---

# Map / Reduce

Map transforms a sequence into another sequence. This is equivalent to a
list comprehension. Comprehensions are usually considered more 'pythonic':
```python
map( lambda x: x**2, [1,2,3] ) # [1, 4, 9]

[ x**2 for x in [1,2,3] ]      # [1, 4, 9]
```

--

Reduce transforms a sequence into a single value. The lambda function takes
two arguments which are the first two elements of the list, and in later
iterations they are the result of the last call and the next element of the
list:
```python
f = lambda a,b: a if (a > b) else b

reduce(f, [47,11,42,102,13]) # 102
```

???
[The reduce example is from an online course.](http://www.python-course.eu/lambda.php)

---

# Modules

Use the `import` keyword to import functions from another module:
```python
import random
from math import floor
floor( random.random() * 100 ) # ???
```

--

You create your own modules by creating a new python file (`*.py`), then you can
import it using the filename minus the extension.

```python
# for file mymodule.py containing function 'myfunction'
import mymodule                 # mymodule.myfunction()
import mymodule.myfunction      # mymodule.myfunction()
from mymodule import myfunction # myfunction()
```

---

# Packages

A package is a directory with multiple modules and an `__init__.py` in it. You 
can import the entire package or individual modules or functions.

```bash
bash$ ls -la mypackage/
total 0
drwxr-xr-x  4 sherman  sherman  136 Jul 29 08:44 .
drwxr-xr-x  9 sherman  sherman  306 Jul 29 08:44 ..
-rw-r--r--  1 sherman  sherman    0 Jul 29 08:44 __init__.py
-rw-r--r--  1 sherman  sherman    0 Jul 29 08:44 mymodule.py
```

--

```python
# we want to use function 'myfunction'
import mypackage                          # mypackage.mymodule.myfunction()
import mypackage.mymodule                 # mypackage.mymodule.myfunction()
from mypackage import mymodule            # mymodule.myfunction()
from mypackage.mymodule import myfunction # myfunction()
```

???
[python tutorial](https://docs.python.org/2/tutorial/modules.html)
[about modules and packages](https://www.learnpython.org/en/Modules_and_Packages)

---

# Classes

Everything in python is an object.

--

Create a class using the class keyword:
```python
class MyClass:
    def myfunc(self, x):
        print(x)

m = MyClass()

m.myfunc(4) # 4
```

--

Use an `__init__` function for a constructor:
```python
class MyClass:
	def __init__(self, foo, bar):
		self.foo = foo
		self.bar = bar
	def printme(self):
		print(self.foo, self.bar)

m = MyClass(5, 7)
m.printme() # (5, 7)
```

---

# Class Participation!

An exercise commonly used in job interviews is Fizz Buzz. We're going to
write a Fizz Buzz solution in python using the skills you just learned.

With the numbers 1 through 100, print 'Fizz' if the number is a multiple of
3, or print 'Buzz' if the number is a multiple of 5. If the number is both a
multiple of 3 and a multiple of 5, print 'Fizzbuzz'. If the number is not a
multiple of either 3 or 5, print the number.

# Solution 1

```python
for x in range(100):
	n = x+1
	if n % 5 == 0 and n % 3 == 0:
		print("fizzbuzz")
	elif n % 3 == 0:
		print("fizz")
	elif n % 5 == 0:
		print("buzz")
	else:
		print(n)
```

# Solution 2

```python
def prn(w):
	print(w)
map( prn,
		[ ( "fizzbuzz" if x % 15 == 0 else
			( "fizz" if x % 3 == 0 else
				( "buzz" if x % 5 == 0 else
					x) ) ) for x in 
				[x+1 for x in range(100)] ])
```

# Done!

You have now completed the tutorial mission. That means you are now
qualified to write python code!

Congratulations on your new skill!
