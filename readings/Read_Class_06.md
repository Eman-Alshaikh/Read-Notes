# How to use Random Module
The random module provides access to functions that support many operations. Perhaps the most important thing is that it allows you to generate random numbers.

When to use it?

We want the computer to pick a random number in a given range Pick a random element from a list, pick a random card from a deck, flip a coin etc. When making your password database more secure or powering a random page feature of your website.

Random functions: 

The Random module contains some very useful functions.

Randint: It is used if we want a random integer  

Random :If you want a larger number, you can multiply it.

Choice: Generate a random value from the sequence sequence.

Shuffle :it shuffles the elements in list in place, so they are in a random order.

Randrange: Generate a randomly selected element from range(start, stop, step).

Code Example :

```
import random
import itertools

outcomes = { 'heads':0,
             'tails':0,
             }
sides = outcomes.keys()

for i in range(10000):
    outcomes[ random.choice(sides) ] += 1

print 'Heads:', outcomes['heads']
print 'Tails:', outcomes['tails']

```
The results are tabulated in a dictionary using the outcome names as keys.

```
$ python random_choice.py

Heads: 4984
Tails: 5016
```
---

## What is Risk Analysis :

In Software Testing, risk analysis is the process of identifying the risks in applications or software that you built and prioritizing them to test.

Why use Risk Analysis?

 it helps the developers and managers to mitigate the risks. 

here is a list of 
 the possible risks that you could encounter:

 - Use of new hardware
- Use of new technology
- Use of new automation tool
- The sequence of code
- Availability of test resources for the application

Risk Assessment :

There are three perspectives of Risk Assessment:

Effect:To assess risk by Effect. In case you identify a condition, event or action and try to determine its impact

Cause :To assess risk by Cause is opposite of by Effect. Initialize scanning the problem and reach to the point that could be the most probable reason behind that.

Likelihood:To assess risk by Likelihood is to say that there is a probability that a requirement won’t be satisfied.

How to perform Risk Analysis?
There are three steps:

1- Searching the risk

2- Analyzing the impact of each individual risk

3-Measures for the risk identified

--- 
## Test Coverage :

Test coverage is a useful tool for finding untested parts of a codebase. Test coverage is of little use as a numeric statement of how good your tests are.

Sufficiency of testing is much more complicated attribute than coverage can answer. I would say you are doing enough testing if the following is true:

- You rarely get bugs that escape into production, and
- You are rarely hesitant to change some code for fear it will cause production bugs.

Can you test too much? Sure you can. You are testing too much if you can remove tests while still having enough. But this is a difficult thing to sense. One sign you are testing too much is if your tests are slowing you down.  

So what is the value of coverage analysis again? 

Well it helps you find which bits of your code aren't being tested. It's worth running coverage tools every so often and looking at these bits of untested code. Do they worry you that they aren't being tested?
