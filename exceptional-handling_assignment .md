ANS 1 :  An **Exception** in Python is an event that occurs during the execution of a program, which disrupts the normal flow of the program's instructions. When a Python script raises an exception, it must either handle the exception immediately otherwise it terminates and quits.

The difference between **Exceptions** and **Syntax errors** in Python are as follows:

- **Syntax errors**: These occur when the parser detects an incorrect statement. For example, if the proper syntax of the language is not followed then a syntax error is thrown⁵. Syntax errors are problems in a program due to which the program will stop the execution.

- **Exceptions**: These are raised when the program is syntactically correct, but the code results in an error. This error does not stop the execution of the program, however, it changes the normal flow of the program. Exceptions are events that are used to modify the flow of control through a program when an error occurs. Exceptions get triggered automatically on finding errors in Python.

In summary, syntax errors occur during parsing (i.e., when Python is reading your code and doesn’t know what to do with it), while exceptions occur during execution (i.e., when syntactically correct Python code results in an error).


Ans2: When an exception is not handled in Python, it terminates the current process and moves it to the calling process to handle the exception. If the calling process also fails to handle the exception, the program crashes.

For example, consider a simple division operation where the denominator is zero:


```python
def division(a, b):
    return a / b

c = division(10, 0)

```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    Cell In[1], line 4
          1 def division(a, b):
          2     return a / b
    ----> 4 c = division(10, 0)
    

    Cell In[1], line 2, in division(a, b)
          1 def division(a, b):
    ----> 2     return a / b
    

    ZeroDivisionError: division by zero


In this case, a ZeroDivisionError is raised because you cannot divide a number by zero. Since this exception is not handled in the code, the Python interpreter will stop the program and output an error message:


```python
def division(a, b):
    try:
        return a / b
    except ZeroDivisionError:
        print("Error: Denominator cannot be 0.")

c = division(10, 0)

```

    Error: Denominator cannot be 0.
    

In this modified code, if a ZeroDivisionError occurs, it will be caught by the except block and a custom error message will be printed instead of terminating the program

Ans3: In Python, the try and except statements are used to catch and handle exceptions.

Here’s how they work:

The try block contains the code that might raise an exception.
The except block catches the exception and defines how the program should respond to it


```python
#Here’s an example:
try:
    # This is the code that might raise an exception
    x = 1 / 0
except ZeroDivisionError:
    # This is how we handle the exception
    print("You can't divide by zero!")

```

    You can't divide by zero!
    

Ans4 : In Python, the try, except, else, finally, and raise statements are used for error and exception handling.

Here’s a brief explanation of each:

try: This block contains the code that might raise an exception.
except: This block catches the exception and defines how the program should respond to it.
else: This block executes if no exception occurs in the try block.
finally: This block always executes, regardless of whether an exception occurs in the try block.
raise: This statement allows you to throw an exception explicitly.
Here’s an example that uses all of these statements: 


```python
def divide(x, y):
    try:
        result = x / y
    except ZeroDivisionError:
        print("Error: You tried to divide by zero.")
        raise
    else:
        print(f"The result is {result}.")
    finally:
        print("Execution of the divide function is complete.")

try:
    divide(10, 0)
except:
    print("An error occurred.")

```

    Error: You tried to divide by zero.
    Execution of the divide function is complete.
    An error occurred.
    

Ans 5 : Custom Exceptions in Python are user-defined exceptions that are created by subclassing the built-in Exception class or any of its subclasses12. Custom exceptions allow you to define your own types of exceptions that can be raised in your program.

We need custom exceptions for several reasons:

They allow us to create specific types of exceptions that can provide more detailed error information.
They can make our code more readable and easier to debug, as the type of exception can give a clear indication of what went wrong.
They allow us to respond differently to different types of exceptions.
Here’s an example of a custom exception in Python:


```python
class InvalidAgeException(Exception):
    """Raised when the input value is less than 18"""
    pass

number = 18
try:
    input_num = int(input("Enter a number: "))
    if input_num < number:
        raise InvalidAgeException
    else:
        print("Eligible to Vote")
except InvalidAgeException:
    print("Exception occurred: Invalid Age")

```

    Enter a number: 17
    Exception occurred: Invalid Age
    

In this example, we have defined a custom exception InvalidAgeException. If the input number is less than 18, the code raises an InvalidAgeException1. The except block catches this exception and prints a custom error message.

Ans 6: here’s an example of how you can create a custom exception class and use it to handle an exception in Python:


```python
class CustomException(Exception):
    """A custom exception class"""
    pass

try:
    # Here we raise our custom exception
    raise CustomException("This is a custom exception")
except CustomException as e:
    # Here we catch and handle the custom exception
    print(f"Caught an exception: {e}")

```

    Caught an exception: This is a custom exception
    

In this code, we first define a custom exception class called CustomException that inherits from the built-in Exception class. Then, in the try block, we raise an instance of our CustomException, passing a string to the constructor that describes the error. In the except block, we catch instances of CustomException and handle them by printing an error message.


```python

```
