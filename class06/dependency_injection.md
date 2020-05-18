# Dependency Injection  
### There are basically three types of dependency injection:  
* __constructor injection__: the dependencies are provided through a class constructor.  
* __setter injection__: the client exposes a setter method that the injector uses to inject the dependency.  
* __interface injection__: the dependency provides an injector method that will inject the dependency into any client passed to it. Clients must implement an interface that exposes a setter method that accepts the dependency.  

### So now its the dependency injection’s responsibility to:

* __Create__ the objects  
* Know which classes __require__ those objects  
* And __provide__ them all those objects  

### References:
* [Five principles of object oriented programming](https://scotch.io/bar-talk/s-o-l-i-d-the-first-five-principles-of-object-oriented-design#toc-single-responsibility-principle)  
* [Inversion of control from freecodecamp](https://www.freecodecamp.org/news/a-quick-intro-to-dependency-injection-what-it-is-and-when-to-use-it-7578c84fa88f/)  


