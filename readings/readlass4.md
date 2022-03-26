#  :red_square: Read: Class 04

 ## :red_square: Classes and Objects
 
  
Objects : are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes.
Classes : are essentially a template to create your objects.

You can create multiple different objects that are of the same class(have the same variables and functions defined).
 However, each object contains independent copies of the variables defined in the class.
 For instance, if we were to define another object with the "MyClass" class and then change the string in the variable above:
 
```
 
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()
myobjecty = MyClass()

myobjecty.variable = "yackity"

# Then print out both values
print(myobjectx.variable)
print(myobjecty.variable)
```
 
:small_blue_diamond: init() :

The __init__() function, is a special function that is called when the class is being initiated.
It's used for asigning values in a class.
 ```
 class NumberHolder:

   def __init__(self, number):
       self.number = number

   def returnNumber(self):
       return self.number

var = NumberHolder(7)
print(var.returnNumber()) #Prints '7'
 ```
 
 
 

  ## :red_square: Thinking Recursively in Python
 
 A recursive function is a function defined in terms of itself via self-referential expressions.

This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result.
All recursive functions share a common structure made up of two parts: base case and recursive case.

To demonstrate this structure, let’s write a recursive function for calculating n!:



Decompose the original problem into simpler instances of the same problem. This is the recursive case:
 ```
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1
n! = n x (n−1)!
 ```


As the large problem is broken down into successively less complex ones, those subproblems must eventually become so simple that they can be solved without further subdivision. This is the base case:

 ```
n! = n x (n−1)! 
n! = n x (n−1) x (n−2)!
n! = n x (n−1) x (n−2) x (n−3)!
⋅
⋅
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3!
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2!
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1!
 ```
Here, 1! is our base case, and it equals 1.

Recursive function for calculating n! implemented in Python:
 ```
def factorial_recursive(n):
    # Base case: 1! = 1
    if n == 1:
        return 1

    # Recursive case: n! = n * (n-1)!
    else:
        return n * factorial_recursive(n-1)
  ```
   ```
>>> factorial_recursive(5)
120
 ```
Behind the scenes, each recursive call adds a stack frame (containing its execution context) to the call stack until we reach the base case.
Then, the stack begins to unwind as each call returns its results:

 :small_blue_diamond: Recursive Data Structures in Python
 
 A data structure is recursive if it can be deﬁned in terms of a smaller version of itself. A list is an example of a recursive data structure.
 Let me demonstrate. Assume that you have only an empty list at your disposal, and the only operation you can perform on it is this:
  ```
  # Return a new list that is the result of
# adding element to the head (i.e. front) of input_list
def attach_head(element, input_list):
    return [element] + input_list
   ```
   Using the empty list and the attach_head operation, you can generate any list. For example, let’s generate [1, 46, -31, "hello"]:
```
attach_head(1,                                                  # Will return [1, 46, -31, "hello"]
            attach_head(46,                                     # Will return [46, -31, "hello"]
                        attach_head(-31,                        # Will return [-31, "hello"]
                                    attach_head("hello", [])))) # Will return ["hello"]
```
```
 
[1, 46, -31, 'hello']
```

Starting with an empty list, you can generate any list by recursively applying the attach_head function,
and thus the list data structure can be defined recursively as:
```
       +---- attach_head(element, smaller list)
list = +
       +---- empty list
```
Recursion can also be seen as self-referential function composition. 
We apply a function to an argument, then pass that result on as an argument to a second application of the same function, and so on. 
Repeatedly composing attach_head with itself is the same as attach_head calling itself repeatedly.

 

  ## :red_square: Pytest Fixtures and Coverage
  
  pytest, it is a library for testing Python code .
  In pytest, you define fixtures using a combination of the pytest.fixture decorator, along with a function definition. 
  For example, say you have a file that returns a list of lines from a file, in which each line is reversed:
  ```
  
def reverse_lines(f):
   return [one_line.rstrip()[::-1] + '\n'
           for one_line in f]
  ```
  
   fixtures are used differently from global variables. 
   For example, let's say you want to include this fixture in one of your tests
   
   You then can mention it in the test's parameter list. Then, inside the test, you can access the fixture by name.  

 
