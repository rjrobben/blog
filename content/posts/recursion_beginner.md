+++ 
draft = false
date = 2022-09-15T18:40:41+08:00
title = "What is recursion from a beginner's view"
description = ""
slug = ""
authors = []
tags = []
categories = []
externalLink = ""
series = []
+++

I always find recursion a difficult concept to grasp, mainly because it's hard to visualize or understand what is exactly going on when you call a function recursively. The recursions can easily go complicated because from the start to the base case (meaning reaching a point where there will be no more recursion) there can be tons of steps. A several layers recursion is already computationally demanding for my brain to visualize. 

Taking the Fibonacci sequence as an example

```python
def fib(n):
    if n<=1:
        return n
    t = fib(n-1) + fib(n-2)
    return t

# code taken from "think like a computer scientist"
```

The code is pretty straightforward, but it's hard to visualize what is going on.

Take n = 7, if one wants to knows what exactly is going on, it already requires a lot of ram of your brian to visual the process behind the scenes. And, to me, this just makes the whole concept so hard to grasp as a person who can better reason on concrete stuff. 

When i try to visualize:

when n=7, t= fib(6) + fib(5)=13n+8n =21

fib(6) =fib(5) + fib(4) = 8n +5n=13

fib(5)= fib(4) + fib(3) = 5n +3n= 8

fib(4) = fib(3) + fib(2) =3n+2n=5
fib(3) = fib(2) + fib(1) =2n+n=3

fib(2) = fib(1)+fib(0) = 2

when n<=1, fib(n)=n=1, which is the base case.

It is not easy to see the logic behind a recursive function call if you don't reach the base case and build up from there. 

As I continue to read on the recursion chapter in "how to think like a computer scientist", it suggests a higher level of abstraction to understand recursion:

1. consider the base case first: when n=0, fib(0)=fib(1)=1. 
2. Assume n=0 and 1 works correctly in fib() function
3. when n=2, fib(2)=fib(1)+fib(0)=2
4. n=2 also works correctly in fib() function
5. Take a "leap of faith" : as base case works and base case +1 also works, it works for any n as any n can be built from n+1
6. try several higher order of n and see if the function works correctly
7. it works! (But how does it work out? ) i dun care. it works.

As you can see, this resembles the mathematics induction proof a lot for those of you who have studied that before. 

We should train the higher level of thinking as we cannot just visualize everything, just visualize it when it doesn't work.

Thanks for reading!
