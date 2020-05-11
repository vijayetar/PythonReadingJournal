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