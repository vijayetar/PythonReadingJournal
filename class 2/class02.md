# Python environment
## Benefits of MODULES 
* __Simplicity__: A module typically focuses on one relatively small portion of the problem. 

* __Maintainability__:  If modules are written in a way that minimizes interdependency, there is decreased likelihood that modifications to a single module will have an impact on other parts of the program. 

* __Reusability__: This eliminates the need to duplicate code.

* __Scoping__: Modules typically define a separate namespace, which helps avoid collisions between identifiers in different areas of a program. 

## MODULES Overview  
* Examples of mod.py file  
* >mod.py
s = "If Comrade Napoleon says it, it must be right."  
a = [100, 200, 300]  
def foo(arg):
    print(f'arg = {arg}')  
class Foo:  
    pass

* So how do we get the module mod.py imported  
> import mod  
> print(mod.s)  
If Comrade Napoleon says it, it must be right.  
> mod.a
[100, 200, 300]  
> mod.foo(['quux', 'corge', 'grault'])
arg = ['quux', 'corge', 'grault']  
> x = mod.Foo()  
> x 

## Path and location matter  
if you do not have the file in the current directory or the input directory, you will have to define the path.
> 
>> sys.path.append(r'C:\Users\john')    
>> sys.path
['', 'C:\\Users\\john\\Documents\\Python\\doc', 'C:\\Python36\\Lib\\idlelib',
'C:\\Python36\\python36.zip', 'C:\\Python36\\DLLs', 'C:\\Python36\\lib',
'C:\\Python36', 'C:\\Python36\\lib\\site-packages', 'C:\\Users\\john']  

>>> import mod  



## [Recursion](https://www.geeksforgeeks.org/recursion/)  
### Definitions  
* The process in which a function calls itself directly or indirectly is called __recursion__ and the corresponding function is called as __recursive function__.  
*  A function fun is called __direct recursive__ if it calls the same function fun. A function fun is called __indirect recursive__ if it calls another function say fun_new and fun_new calls fun directly or indirectly.  
*  A recursive function is __tail recursive__ when recursive call is the last thing executed by the function. 
* If the base case is not reached or not defined, then the __stack overflow__ problem may arise.  
*  When any function is called from main(), the __memory is allocated to it on the stack__. A recursive function calls itself, the memory for a called function is allocated on top of memory allocated to calling function and different copy of local variables is created for each function call. When the base case is reached, the function returns its value to the function by whom it is called and memory is __de-allocated__ and the process continues.  

### Recursive vs iterative programming  
* The recursive program has greater space requirements than iterative program as all functions will remain in the stack until the base case is reached. 
* Recursion provides a clean and simple way to write code. Some problems are inherently recursive like tree traversals  
