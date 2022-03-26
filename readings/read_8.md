## List Comprehensions:

It’s recommended that you use Python’s comprehension features , to keep your code elegant and readable.

List comprehension : is a powerful and concise method for creating lists in Python that becomes essential the more you work with lists, and lists of lists.
# Syntax :

my_new_list = [ expression for item in list ]

You can see from this example that three ingredients are necessary for a python list comprehension to work.

1- First is the expression we’d like to carry out. expression inside the square brackets.

2- Second is the object that the expression will work on. item inside the square brackets.

3- Finally, we need an iterable list of objects to build our new list from. list inside the square brackets.

# Notes about Lists Comprehensions

- List comprehension methods are an elegant way to create and manage lists. 
- In Python, list comprehensions are a more compact way of creating lists. 
- More flexible than for loops, list comprehension is usually faster than other methods.

**Creating a list with list comprehensions
```
# construct a basic list using range() and list comprehensions
# syntax
# [ expression for item in list ]
digits = [x for x in range(10)]

print(digits)
```
Output

```
 [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

In the python example above, we’re using the range() method to generate a list of numbers. Python iterates(or loops) through each item in that range, and saves a copy of the item in a new list called digits.

Create a List Using Loops and List Comprehension in Python
To better illustrate how a list comprehension can be used to write more efficient Python code, we’ll take a look at a side by side comparison. 

In the following example, you’ll see two different techniques for creating a Python list. The first is a for loop. We’ll use it to construct a list of the powers of two.

- Comparing list creation methods in Python

First, create a list and loop through it. Add an expression, in this example, we’ll raise x to the power of 2.
```
# create a list using a for loop
squares = []

for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares)
```
output :
```
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

The same thing can be done using a list comprehension, but with a fraction of the code. Let’s take a look at how to create a list of squares using the list comprehension method.
```
# create a list using list comprehension
squares = [x**2 for x in range(10)]

print(squares)
```
Even in this basic example, it’s obvious that list comprehensions reduce the code necessary to complete rather complicated task when working with a list.

- Separating the characters in a string
```
use list comprehension to print the letters in a string
letters = [ letter for letter in "20,000 Leagues Under The Sea"]

print(letters)
```
Output
```
['2', '0', ',', '0', '0', '0', ' ', 'L', 'e', 'a', 'g', 'u', 'e', 's', ' ', 'U', 'n', 'd', 'e', 'r', ' ', 'T', 'h', 'e', ' ', 'S', 'e', 'a']
```

- Lower/Upper case converter using Python:

Using list comprehension to loop through a string in Python, it’s possible to convert strings from lower case to upper case, and vice versa. 

Changing a letter’s case
```
lower_case = [ letter.lower() for letter in ['A','B','C'] ]
upper_case = [ letter.upper() for letter in ['a','b','c'] ]

print(lower_case, upper_case)
```
Output
```
['a', 'b', 'c'] ['A', 'B', 'C']
```

- Print numbers only from a given string:

Another interesting exercise is to extract numbers from a string. For example, we may have a database of names and phone numbers.
```
# user data entered as name and phone number
user_data = "Elvis Presley 987-654-3210"
phone_number = [ x for x in user_data if x.isdigit()]

print(phone_number)
```
Output
```
['9', '8', '7', '6', '5', '4', '3', '2', '1', '0']
```
- Using functions in list comprehensions:

So far we’ve seen how to use list comprehension to generate lists using some basic Python methods like lower() and upper(). But what if we wanted to use our own Python functions?

Adding arguments to list comprehension
```
# list comprehension with functions
# create a function that returns a number doubled
def double(x):
    return x*2

nums = [double(x) for x in range(1,10)]
print(nums)
```
Output


```
[2, 4, 6, 8, 10, 12, 14, 16, 18]

```


In conclusion, hopefully you’ve seen the potential of list comprehensions and how they can be used to write more elegant Python code. Writing compact code is essential for maintaining programs and working with teams. 

---
## Primer on Python Decorators

By definition, a decorator is a function that takes another function and extends the behavior of the latter function without explicitly modifying it.

Returning Functions From Functions
Python also allows you to use functions as return values. The following example returns one of the inner functions from the outer parent() function:
```
def parent(num):
    def first_child():
        return "Hi, I am Emma"

    def second_child():
        return "Call me Liam"

    if num == 1:
        return first_child
    else:
        return second_child
```
Note that you are returning first_child without the parentheses. Recall that this means that you are returning a reference to the function first_child. In contrast first_child() with parentheses refers to the result of evaluating the function. This can be seen in the following example:
```
>>> first = parent(1)
>>> second = parent(2)

>>> first
<function parent.<locals>.first_child at 0x7f599f1e2e18>

>>> second
<function parent.<locals>.second_child at 0x7f599dad5268>
```
The somewhat cryptic output simply means that the first variable refers to the local first_child() function inside of parent(), while second points to second_child().

You can now use first and second as if they are regular functions, even though the functions they point to can’t be accessed directly:
    ```

>>> first()
'Hi, I am Emma'

>>> second()
'Call me Liam'
```
Finally, note that in the earlier example you executed the inner functions within the parent function, for instance first_child(). However, in this last example, you did not add parentheses to the inner functions—first_child—upon returning.