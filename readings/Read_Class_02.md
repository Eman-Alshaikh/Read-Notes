#  :red_square: Read: Class 02.
 ## :red_square: In Tests We Trust - TDD with Python
  
Unit tests are some pieces of code to exercise the input, the output and the behaviour of your code. You can write them anytime you want.
Important aspects about the unit test

:small_blue_diamond: We need to be descriptive about it and to say what is expected and what we are testing

:small_blue_diamond: The test file name should follow the same name of module name

:small_blue_diamond:It’s ideal to separate the tests folder from production code (the implementation)

:small_blue_diamond:Other thing to care about is the structure. A convention widely used is the AAA: Arrange, Act and Assert.

:small_blue_diamond:When we are writing tests we are forced to think about the design first and how we can break it into small pieces.


The test cycle is made by three steps:

🆘 Write a unit test and make it fail .

✅ Write the feature and make the test pass!  

🔵 Refactor the code  .

  ## :red_square: If name equals main
 
 If the python interpreter is running that module (the source file) as the main program, it sets the special __name__ variable to have a value “__main__”. 
If this file is being imported from another module, __name__ will be set to the module’s name. Module’s name is available as value to __name__ global variable. 

Advantages for using If name equals main:

:small_blue_diamond:Every Python module has it’s __name__ defined and if this is ‘__main__’, it implies that the module is being run standalone by the user and we can do corresponding appropriate actions.

:small_blue_diamond:If you import this script as a module in another script, the __name__ is set to the name of the script/module.

:small_blue_diamond:Python files can act as either reusable modules, or as standalone programs.

:small_blue_diamond:if __name__ == “main”: is used to execute some code only if the file was run directly, and not imported.


  ## :red_square: Recursion
  
  What is Recursion? 
The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function. Using recursive algorithm, certain problems can be solved quite easily

:small_blue_diamond:How a particular problem is solved using recursion? 
The idea is to represent a problem in terms of one or more smaller problems,
 and add one or more base conditions that stop the recursion. For example, we compute factorial n if we know factorial of (n-1). The base case for factorial would be n = 0. We return 1 when n = 0. 
