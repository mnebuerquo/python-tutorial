# Sherman's Python Tutorial

Let's learn some basics of python.

We'll assume you already have python 2.7 installed.

???
Does Sherman really know python?

---

# Running Python Interactively

The `python` command starts the python interpreter.

```
bash$ python
Python 2.7.12 (default, Oct 11 2016, 05:24:00)
[GCC 4.2.1 Compatible Apple LLVM 8.0.0 (clang-800.0.38)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
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

---

# Variables in Python

You create a variable just by assigning to it. No `var` or other
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

# Sequence Types

There are six sequence types in python: str, unicode, list, tuple, buffer, xrange.
We are going to talk about str, list, tuple.

--

Access elements of a sequence using brackets:
```python
x = "bar"
print(x[0]) # b
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
type. Lists can be mutated.
```python
mylist = [ "foo", "bar", "baz", "wow" ]
mylist[4] = "new"
print( mylist[4] ) # prints "new"
```

--

Tuples are created with parentheses. They can not be appended nor can elements be replaced.
You would have to create a new tuple with different elements instead.
```python
mytuple = (1, "foo", 3.14159265)
print( mytuple[1] ) # prints "foo"
mytuple[1] = "bar" # TypeError: 'tuple' object does not support item assignment
```

---

# Slices

```python
seq = [ 1, 2, 3, 4, 5 ]
```

Slice `seq[ start : stop ]` returns a slice from the sequence, where
`start` is the first element in the slice, and `stop` is the element
after the slice.
```python
seq[1:3] # [ 2, 3 ]
```

--

Slices with negative indexes count backwards from the end of the list:
```python
seq[-1]   # 5
seq[1:-1] # [ 2, 3, 4 ]
seq[-3:3] # [ 3 ]
seq[-1:1] # []
```

--

You may omit either index in the slice to read from the start or to the end
of the list:
```python
seq[2:]  # [ 3, 4, 5 ]
seq[:3]  # [ 1, 2, 3 ]
seq[-2:] # [ 4, 5 ]
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

# Control Flow

Python defines blocks by indenting then code in the inner block.

The `if` statement executes the indented code block if the condition
evaluates to `True`:
```python
if condition :
	statement
elif condition :
	statement
else :
	statement
```

---

# Pass

Sometimes you need a statement to complete the syntax, but you do not need
to execute any operation. Use pass as a null statement:
```python
if 3 < 5 :
	pass # does nothing
else
	pass # does nothing
```

---

# Loops

The for loop iterates over a sequence:
```python
for name in [ "bob", "sam", "ben", "sue", "bev" ] :
	print(name)
```

--

You can use the range function to use a numeric counter:
```python
for i in range(10):
	pass
```

--

The while loop iterates as long as a condition is true:
```python
i = 0
while i < 10 :
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
	pass
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
	print("else")
print("done")
```

---

# Functions

def

--

return

---

# Function vs Global Scope

global keyword

# Function Arguments

default

--

keyword

--

extended

---

# Lambda Forms

---

# Map / Reduce

---

# Modules

---

# Classes

---

# Done!

You have now completed the tutorial mission.

???
Thank you for attending.
