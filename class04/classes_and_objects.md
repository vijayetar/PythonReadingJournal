# Python Classes/Objects
[Reference](https://www.w3schools.com/python/python_classes.asp)

* Python is an object oriented programming language.

* Almost everything in Python is an object, with its properties and methods.

* A Class is like an object constructor, or a "blueprint" for creating objects.

* Create Class  
> class MyClass:  
  x = 5

* Create object  
> p1 = MyClass()  
print(p1.x)  

* All classes have a function called __init__(), which is always executed when the class is being initiated.  

> class Person:  
  def \__init__(self, name, age):  
    self.name = name  
    self.age = age  
p1 = Person("John", 36) 

* Objects can also contain methods. Methods in objects are functions that belong to the object. 

*  > def myfunc(self):  
    print("Hello my name is " + self.name)  
p1 = Person("John", 36)  
p1.myfunc()  

 * The self parameter is a reference to the current instance of the class, and is used to access variables that belong to the class.  

 * Modify:  
 > p1.age = 40

 * Delete:  
 > del p1  
 
