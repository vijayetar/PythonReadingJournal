# Syntax and Exception Errors
## Exceptions versus Syntax Errors
* __Syntax errors__ occur when the parser detects an incorrect statement.  
* __Exception error__ occurs whenever syntactically correct Python code results in an error. The last line of the message indicated what type of exception error you ran into. 
1. Use __raise__ to throw an exception if a condition occurs  

![Raise an error](https://files.realpython.com/media/raise.3931e8819e08.png)
> if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))  
2. __Assertion error__ exception is that we assert that a certain condition is met. If this condition turns out to be True, then that is excellent! The program can continue. If the condition turns out to be False, you can have the program throw an AssertionError exception.  

![AssertionError](https://files.realpython.com/media/assert.f6d344f0c0b4.png)

>assert ('linux' in sys.platform), "This code runs on Linux only."  

3. The __try and except__ block in Python is used to catch and handle exceptions. Python executes code following the try statement as a “normal” part of the program. The code that follows the except statement is the program’s response to any exceptions in the preceding try clause.  

![Try and Except](https://files.realpython.com/media/try_except.c94eabed2c59.png)

>   try:    
      linux_interaction()  
    except AssertionError as error:  
      print(error)  
      print('The linux_interaction() function was not executed')  

>   try:  
    with open('file.log') as file:  
        read_data = file.read()  
except FileNotFoundError as fnf_error:  
    print(fnf_error)  

__you’ll want to refer to specific exception classes you want to catch and handle__

>   try:  
      linux_interaction()
      with open('file.log') as file:  
        read_data = file.read()  
    except FileNotFoundError as fnf_error:  
      print(fnf_error)  
    except AssertionError as error:  
      print(error)  
      print('Linux linux_interaction()   function was not executed')  

4. In Python, using the else statement, you can instruct a program to execute a certain block of code only in the absence of exceptions.    
![catvh](https://files.realpython.com/media/try_except_else.703aaeeb63d3.png) 

5. Finally is some sort of action to clean up after executing your code. 
![try except else finally](https://files.realpython.com/media/try_except_else_finally.a7fac6c36c55.png)   
finally enables you to execute sections of code that should always run, with or without any previously encountered exceptions.
