# Python Scopes and LEGB  
[Home](../README.md)
### Python Scopes  
* *hat scopes are and how they work in Python  
* Why it’s important to know about Python scope  
* What the LEGB rule is and how Python uses it to resolve names  
* How to modify the standard behavior of Python scope using global and nonlocal  
* What scope-related tools Python offers and how you can use them  

__Global scope__: The names that you define in this scope are available to all your code.

__Local scope__: The names that you define in this scope are only available or visible to the code within the scope.

Names at the top level of a module are stored in the module’s namespace. In other words, they’re stored in the module’s .__dict__ attribute.   

### LEGB (local, enclosing, global and built-in)  

__Local (or function) scope__ is the code block or body of any Python function or lambda expression. This Python scope contains the names that you define inside the function. These names will only be visible from the code of the function.  

* Whenever you try to access a name that isn’t defined in any Python scope, you’ll get a NameError. The error message will include the name that couldn’t be found.  

* > In a code example, you inspect .\__code__ on square(). This is a special attribute that holds information about the code of a Python function. In this case, you see that .co_varnames holds a tuple containing the names that you define inside square().  

__Enclosing (or nonlocal) scope__ is a special scope that only exists for nested functions. If the local scope is an inner or nested function, then the enclosing scope is the scope of the outer or enclosing function.  

* > Note that inner_func() is only visible to the code in outer_func().  

* Last but not least, you can’t modify names in the enclosing scope from inside a nested function unless you declare them as nonlocal in the nested function.   

__Global (or module) scope__ is the top-most scope in a Python program, script, or module.  

* Python turns your program’s main script into a module called \__main__ to hold the main program’s execution. The namespace of this module is the main global scope of your program.  

* > When you call dir() with no arguments, you get the list of names available in your main global Python scope.  


__Built-in scope__ is a special Python scope that’s created or loaded whenever you run a script or open an interactive session. This scope contains names such as keywords, functions, exceptions, and other attributes that are built into Python.  
* Notice that the names in builtins are always loaded into your global Python scope with the special name __builtins__, as you can see in the following code:  
> >>> len(dir(__builtins__))
152  


> * Inside inner_func(): This is the local scope, but number doesn’t exist there.  
 > * Inside outer_func(): This is the enclosing scope, but number isn’t defined there either.  
> * In the module scope: This is the global scope, and you find number there, so you can print number to the screen.  
> * If number isn’t defined inside the global scope, then Python continues the search by looking at the built-in scope.  





