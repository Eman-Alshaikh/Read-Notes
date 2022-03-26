## Python Scope

The scope of a name defines the area of a program in which you can unambiguously access that name, such as variables, functions, objects, and so on.


The names in your programs will have the scope of the block of code in which you define them. When you can access the value of a given name from someplace in your code, you’ll say that the name is in scope. If you can’t access the name, then you’ll say that the name is out of scope.

Python uses the location of the name assignment or definition to associate it with a particular scope. In other words, where you assign or define a name in your code determines the scope or visibility of that name.

For example, if you assign a value to a name inside a function, then that name will have a local Python scope. In contrast, if you assign a value to a name outside of all functions—say, at the top level of a module—then that name will have a global Python scope.

 The Python scope concept is generally presented using a rule known as the LEGB (Local, Enclosing, Global, and Built-in)rule.

 Here’s a quick overview of what these terms mean:

- Local (or function) scope : is the code block or body of any Python function or lambda expression.
 This Python scope contains the names that you define inside the function. These names will only be visible from the code of the function. It’s created at function call, not at function definition, so you’ll have as many different local scopes as function calls.  

- Enclosing (or nonlocal) scope: is a special scope that only exists for nested functions. If the local scope is an inner or nested function, then the enclosing scope is the scope of the outer or enclosing function.  

- Global (or module) scope :is the top-most scope in a Python program, script, or module. This Python scope contains all of the names that you define at the top level of a program or a module. Names in this Python scope are visible from everywhere in your code.

- Built-in scope : is a special Python scope that’s created or loaded whenever you run a script or open an interactive session. This scope contains names such as keywords, functions, exceptions, and other attributes that are built into Python. Names in this Python scope are also available from everywhere in your code. It’s automatically loaded by Python when you run a program or script.




# Functions: The Local Scope
The local scope or function scope is a Python scope created at function calls. Every time you call a function, you’re also creating a new local scope. On the other hand, you can think of each def statement and lambda expression as a blueprint for new local scopes. These local scopes will come into existence whenever you call the function at hand.

By default, parameters and names that you assign inside a function exist only within the function or local scope associated with the function call. When the function returns, the local scope is destroyed and the names are forgotten. Here’s how this works:
```

>>> def square(base):
...     result = base ** 2
...     print(f'The square of {base} is: {result}')
...
>>> square(10)
The square of 10 is: 100
>>> result  # Isn't accessible from outside square()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    result
NameError: name 'result' is not defined
>>> base  # Isn't accessible from outside square()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    base
NameError: name 'base' is not defined
>>> square(20)
The square of 20 is: 400
```

square() is a function that computes the square of a given number, base.

 When you call the function, Python creates a local scope containing the names base (an argument) and result (a local variable). After the first call to square(), base holds a value of 10 and result holds a value of 100. 
 
 The second time, the local names will not remember the values that were stored in them the first time the function was called. Notice that base now holds the value 20 and result holds 400.

Since you can’t access local names from statements that are outside the function, different functions can define objects with the same name. Check out this example:

```
>>> def cube(base):
...     result = base ** 3
...     print(f'The cube of {base} is: {result}')
...
>>> cube(30)
The cube of 30 is: 27000
```
Notice that you define cube() using the same variable and parameter that you used in square(). However, since cube() can’t see the names inside the local scope of square() and vice versa, both functions work as expected without any name collision.

# Nested Functions: The Enclosing Scope

Enclosing or nonlocal scope is observed when you nest functions inside other functions. The enclosing scope was added in Python 2.2. It takes the form of the local scope of any enclosing function’s local scopes. Names that you define in the enclosing Python scope are commonly known as nonlocal names. Consider the following code:
```
>>> def outer_func():
...     # This block is the Local scope of outer_func()
...     var = 100  # A nonlocal var
...     # It's also the enclosing scope of inner_func()
...     def inner_func():
...         # This block is the Local scope of inner_func()
...         print(f"Printing var from inner_func(): {var}")
...
...     inner_func()
...     print(f"Printing var from outer_func(): {var}")
...
>>> outer_func()
Printing var from inner_func(): 100
Printing var from outer_func(): 100
>>> inner_func()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'inner_func' is not defined
```
When you call outer_func(), you’re also creating a local scope. The local scope of outer_func() is, at the same time, the enclosing scope of inner_func(). From inside inner_func(), this scope is neither the global scope nor the local scope. It’s a special scope that lies in between those two scopes and is known as the enclosing scope.

 

All the names that you create in the enclosing scope are visible from inside inner_func(), except for those created after you call inner_func(). Here’s a new version of outer_fun() that shows this point:
```
>>> def outer_func():
...     var = 100
...     def inner_func():
...         print(f"Printing var from inner_func(): {var}")
...         print(f"Printing another_var from inner_func(): {another_var}")
...
...     inner_func()
...     another_var = 200  # This is defined after calling inner_func()
...     print(f"Printing var from outer_func(): {var}")
...
>>> outer_func()
Printing var from inner_func(): 100
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    outer_func()
  File "<stdin>", line 7, in outer_func
    inner_func()
  File "<stdin>", line 5, in inner_func
    print(f"Printing another_var from inner_func(): {another_var}")
NameError: free variable 'another_var' referenced before assignment in enclosing
 scope
```

When you call outer_func() the code runs down to the point in which you call inner_func(). The last statement of inner_func() tries to access another_var. At this point, another_var isn’t defined yet, so Python raises a NameError because it can’t find the name that you’re trying to use.

---

## Don’t be CONFUSED by BIG O notation anymore!
 


the explanations about Big O notation tend to get very mathematical, this video gives you: :

- an overview of a basic explanation of what is the Big O notation.

Big O notation is a measure of how long an algorithm takes to do something in its basic level at the most basic level that’s what it is that’s the time complexity component and the space complexity component of it is how much memory it takes up whilst it’s doing it how many of your computer’s resources is it allocating to itself in order to do what you’ve asked of it.

- why it’s necessary.

it’s a way of comparing algorithms with each other and it’s a way of finding out how your algorithm will perform once you start sending a lot of data at it so most modern computers will be able to process data quickly if you’re just using it to process a small amount of data but what becomes really important especially if you’re designing something that is mission-critical either for a business that’s processing numerous transaction millions of transactions every day or a system that is vital for keeping patients safe in a hospital or an airplane system.

 