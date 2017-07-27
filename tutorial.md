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

# Strings in Python

Strings are written using double quotes. Strings can be concatenated using
the `+` operator.

```python
x = "this is a "
y = "test"
print(x+y) # prints "this is a test"
print( len(x+y) ) # prints 14
```

---

# Sequence Types

There are six sequence types in python: str, unicode, list, tuple, buffer, xrange.
We are going to talk about str, list, tuple. (We already mentioned strings
in the last slide.)

--

Access elements of a sequence using brackets:
```python
x = "bar"
print(x[0]) # b
print(x[2]) # r
```

--

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

# Done!

You have now completed the tutorial mission.

???
Thank you for attending.
