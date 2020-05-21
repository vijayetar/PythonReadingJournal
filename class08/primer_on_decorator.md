# Primer On Decorator
[Home](../README.md)  
[Referenes](https://realpython.com/primer-on-python-decorators/)  

Decorators provide a simple syntax for calling __higher-order functions__.

## Functions as First-Class Objects
In Python, functions are __first-class objects__. This means that functions can be passed around and used as arguments, just like any other object (string, int, float, list, and so on).  

It’s possible to define functions inside other functions. Such functions are called __inner functions__.  

The inner functions are not defined until the parent function is called. They are __locally scoped__ to parent(): __they only exist inside the parent() function as local variables__.

Python also allows you to use functions as return values, this means that you are returning a reference to the function.  

## Simple Decorators  


