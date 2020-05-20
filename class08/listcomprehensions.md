# List Comprehensions
[Home](../README.md)  
[Referenes](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)  

List comprehensions provide a concise way to create lists.   

* It consists of brackets containing an expression followed by a for clause, then
zero or more for or if clauses. The expressions can be anything, meaning you can
put in all kinds of objects in lists.  

* The result will be a new list resulting from evaluating the expression in the
context of the for and if clauses which follow it.   

* The list comprehension always returns a result list.   

> new_list = [expression(i) for i in old_list if filter(i)]  
> new_list = []  
for i in old_list:  
    if filter(i):  
        new_list.append(expressions(i))  

> \*result*  = [\*transform*    \*iteration*         \*filter*     ]  

>  [x+y for x in [10,30,50] for y in [20,40,60]]  
[30, 50, 70, 50, 70, 90, 70, 90, 110]  



