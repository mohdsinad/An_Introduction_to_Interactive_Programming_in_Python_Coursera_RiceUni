# Question 1
  What typically calls an event handler?  

### Answer
    Some code that you didn't write which generates the event.

----
# Question 2
  In CodeSkulptor, how many event handlers can be running at the same time?  

### Answer
    1

----
# Question 3
  What are the three parts of a frame?  

### Answer
      Control Area  
      Status Area  
      Canvas  

----
# Question 4
  For the SimpleGUI-based programs in this course, we recommended breaking down an interactive Python program into seven parts. Below, these parts are listed alphabetically.  

    1) Create frame  
    2) Define classes  
    3) Define event handlers  
    4) Initialize global variables  
    5) Define helper functions  
    6) Register event handlers  
    7) Start frame and timers  

  Enter 7 numbers in the range 1-7, separated only by spaces, to indicate the recommended ordering of the preceding elements of an interactive Python program.

### Answer
    4 5 2 3 1 6 7

----
# Question 5
  Assume the following global definition is part of your program, `x = 5`, If each of the following function definitions are also part of your program, which of them **needs** a global `x` declaration?

### Explanation

1) def c(y):  
    return x + y

   This example does not need a global declaration. You don't need a `global` declaration unless you are assigning to the global variable.

2) def d(y):  
    y = x + y  
    return y

   This example does not need a global declaration. You don't need a `global` declaration unless you are assigning to the global variable.  

3) def b(x,y):  
    x = x + y  
    return x  

   This example does not need a global declaration. Here a local variable `x` is being assigned to. If you add a `global` declaration, you'll get a SyntaxError.  

4) def a(y):  
    x = x + y  
    return y  

   This example does not need a global declaration. You don't need a `global` declaration unless you are assigning to the global variable.  

----
# Question 6
  Consider the following code.  
    count = 0  

    def square(x):  
        global count  
        count += 1  
        return x**2  

    print square(square(square(square(3))))  

  What is the value of count at the end? Enter a number.  

### Answer
    4

### Explanation
    Each time `square` is called the global variable `count` is increased by 1.

----
# Question 7
----------

Consider the following code.  

a = 3  
b = 6  

def f(a):  
    &nbsp;&nbsp;&nbsp;&nbsp;c = a + b  
    &nbsp;&nbsp;&nbsp;&nbsp;return c  

Which names occur in the global scope?  

### Answer

b, f, a  

Question 8
----------

Consider the following code.  

a = 3  
b = 6  

def f(a):  
    &nbsp;&nbsp;&nbsp;&nbsp;c = a + b  
    &nbsp;&nbsp;&nbsp;&nbsp;return c  

Which names occur in the local scope?   

### Answer

c, a  

Question 9
----------

Which of the following are valid calls to `create_frame`?   

### Answer

`f = simplegui.create_frame("My Frame", 100, 100)`  
`frame = simplegui.create_frame("Testing", 200, 200, 300)`

### Explanation

`frame = simplegui.create_frame(100, 100, 100)`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This is not a valid call. The call is missing title argument.  

`frame = simplegui.create_frame("My Frame", 200, 200, 200, 200)`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This is not a valid call. The call has too many arguments.  

Question 10
-----------

Which of the following are valid ways of making a canvas with a red background?  

### Answer

import simplegui  
frame = simplegui.create_frame("My Frame", 100, 100)  
frame.set_canvas_background("Red")  
frame.start()  

import simplegui  
frame = simplegui.create_frame("My Frame", 100, 100)  
frame.set_canvas_background("red")  
frame.start()  

Quiz
====

Question 1
----------

In the following code, what does the number `100` represent?  
`my_button = frame.add_button("My Label", button_handler, 100)`  

### Answer

Width of the button in pixels.  

Question 2
----------

How many control objects are allowed in a frame?  

### Answer

Unlimited, i.e., 0 or more  

Question 3
----------

In SimpleGUI, one kind of object can be added to the control panel that doesn't allow any handler. Thus, this object can't respond to anything. What kind of object is that?  

### Answer

Label  

Question 4
----------

When you enter text into an input field and press enter, the text is passed to the input field's event handler. What is the data type of the text?    

### Answer

A string  

### Explanation  

The entered data is a string. The text entered into an input field is always passed to the input handler as a string even if the text corresponds to a number.  

Question 5
----------

Consider the following conditional statement.  

if p == False:  
&nbsp;&nbsp;&nbsp;&nbsp;return False  
elif q == False:  
&nbsp;&nbsp;&nbsp;&nbsp;return False  
else:  
&nbsp;&nbsp;&nbsp;&nbsp;return True  

That is equivalent to which of the following simpler statements?

### Answer

return q and p

Question 6
----------

Which of the following describes the mistake in the following code?  

def volume_cube(side):  
&nbsp;&nbsp;&nbsp;&nbsp;""" Returns the volume of a cube, given the length of its side. """  
&nbsp;&nbsp;&nbsp;&nbsp;print side ** 3  

s = 5  
print "The volume of a cube with sides", s, "long is", volume_cube(s), "."  

### Answer

The function should return, not print, its result.  

### Explanation

In most cases, functions should return their computed results. Furthermore, the documentation string here specifies that it should be returning that value.

Question 7
----------

What kind of errors can happen if you are missing a needed `global` declaration in one of your function definitions? For this question, you need only consider the case where the problem is in the function that is missing the `global` declaration.  

### Answer

An incorrect computation that generates no error message  

### Explanation

If you only assign to the variable, without trying to use its current value, you won't get any error message. Instead, Python assumes the variable is local, which might lead to an unexpected result.  

Question 8
----------

Which of the following function definitions are in the recommended code style?     

### Answer

def f(x, y):  
&nbsp;&nbsp;&nbsp;&nbsp;""" Add the two inputs. """  
&nbsp;&nbsp;&nbsp;&nbsp;return x + y  

### Explanation

1. def f (x, y):  
   &nbsp;&nbsp;&nbsp;&nbsp;""" Add the two inputs. """  
   &nbsp;&nbsp;&nbsp;&nbsp;return x + y  

   This does not follow recommended style, there shouldn't be a space before the parenthesis  

2. def myFunction(x, y):  
   &nbsp;&nbsp;&nbsp;&nbsp;""" Add the two inputs. """  
   &nbsp;&nbsp;&nbsp;&nbsp;return x + y  

   This does not follow recommended style, only class names should use "camel case".  

3. def f(x, y):  
   &nbsp;&nbsp;&nbsp;&nbsp;""" Add the two inputs. """  
   &nbsp;&nbsp;&nbsp;&nbsp;return x+y  

   This does not follow recommended style, there should be spaces around the addition operator.  

Question 9
----------

Cut and paste the following code into CodeSkulptor. Run it and make an attempt to understand how it works.  
We'd like to modify the code so that the count is reset to zero whenever a new message is entered. Where would you need to modify this code to implement this change?  

### Answer

Add an assignment to count in the event handler for the input field. Also add a global count declaration there.  

Question 10
-----------

In the game "Guess the number", what is the minimum number of guesses necessary to guarantee that the guesser can always win if the secret number is chosen in range(0, 400)?
Review the mini-project description for "Guess the number" if you are having trouble with this problem.  

### Answer

9 guesses

### Explanation

log to the base 2 (400) rounded to the higher side.  
