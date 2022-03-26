# :red_square:  Read & Write Files in Python
a file is a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable
Files on most modern file systems are composed of three main parts:

Header: metadata about the contents of the file (file name, size, type, and so on)
Data: contents of the file as written by the creator or editor
End of file (EOF): special character that indicates the end of the file

File Paths
When you access a file on an operating system, a file path is required. The file path is a string that represents the location of a file. It’s broken up into three major parts:

Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)
File Name: the actual name of the file
Extension: the end of the file path pre-pended with a period (.) used to indicate the file type

When you want to work with a file, the first thing to do is to open it. 
This is done by invoking the open() built-in function. open() has a single required argument that is the path to the file. open() has a single return, the file object:
```
file = open('dog_breeds.txt')
```

After you open a file, the next thing to learn is how to close it.
there are two ways that you can use to ensure that a file is closed properly, even when encountering an error. The first way to close a file is to use the try-finally block:
```
reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()
```

The second way to close a file is to use the with statement:
```
with open('dog_breeds.txt') as reader:
    # Further file processing goes here

```

There are three different categories of file objects:

Text files: it is the most common file that you’ll encounter.
Buffered binary files: it is used for reading and writing binary files.
Raw binary files:generally used as a low-level building-block for binary and text streams

__file__
The __file__ attribute is a special attribute of modules, similar to __name__. It is:

“the pathname of the file from which the module was loaded, if it was loaded from a file.”
Working With Two Files at the Same Time
There are times when you may want to read a file and write to another file at the same time. If you use the example that was shown when you were learning how to write to a file, it can actually be combined into the following:

```

d_path = 'dog_breeds.txt'
d_r_path = 'dog_breeds_reversed.txt'
with open(d_path, 'r') as reader, open(d_r_path, 'w') as writer:
    dog_breeds = reader.readlines()
    writer.writelines(reversed(dog_breeds))
```

# :red_square: Exceptions in Python

exception error. This type of error occurs whenever syntactically correct Python code results in an error. 
If you want to throw an error when a certain condition occurs using raise, you could go about it like this:

```
x = 10
if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
```

When you run this code, the output will be the following:
```
Traceback (most recent call last):
  File "<input>", line 4, in <module>
Exception: x should not exceed 5. The value of x was: 10
```

The AssertionError Exception
Instead of waiting for a program to crash midway, you can also start by making an assertion in Python. We assert that a certain condition is met. If this condition turns out to be True, then that is excellent! The program can continue. If the condition turns out to be False, you can have the program throw an AssertionError exception.
The try and except Block: Handling Exceptions
The try and except block in Python is used to catch and handle exceptions. Python executes code following the try statement as a “normal” part of the program. The code that follows the except statement is the program’s response to any exceptions in the preceding try clause.

raise allows you to throw an exception at any time.
assert enables you to verify if a certain condition is met and throw an exception if it isn’t.
In the try clause, all statements are executed until an exception is encountered.
except is used to catch and handle the exception(s) that are encountered in the try clause.
else lets you code sections that should run only when no exceptions are encountered in the try clause.
finally enables you to execute sections of code that should always run, with or without any previously encountered exceptions.




