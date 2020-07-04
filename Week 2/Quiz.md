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
      def c(y):  
        return x + y

   This example does not need a global declaration. You don't need a `global` declaration unless you are assigning to the global variable.

      def d(y):  
        y = x + y  
        return y

   This example does not need a global declaration. You don't need a `global` declaration unless you are assigning to the global variable.  

      def b(x,y):  
        x = x + y  
        return x  

   This example does not need a global declaration. Here a local variable `x` is being assigned to. If you add a `global` declaration, you'll get a SyntaxError.  

      def a(y):  
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
    Each time square is called the global variable count is increased by 1.

----
# Question 7
  Consider the following code.

    a = 3
    b = 6

    def f(a):
        c = a + b
        return c

  Which names occur in the global scope?

### Answer
    b f a

----
# Question 8
  Consider the following code.

    a = 3
    b = 6

    def f(a):
        c = a + b
        return c

  Which names occur in the local scope?

### Answer
    c a

----
# Question 9
  Which of the following are valid calls to `create_frame`?

### Answer
      f = simplegui.create_frame("My Frame", 100, 100)
      frame = simplegui.create_frame("Testing", 200, 200, 300)

### Explanation
    frame = simplegui.create_frame(100, 100, 100) : This is not a valid call. The call is missing title argument.
    frame = simplegui.create_frame("My Frame", 200, 200, 200, 200) : This is not a valid call. The call has too many arguments.

----
# Question 10
  Which of the following are valid ways of making a canvas with a red background?

### Answer
*     import simplegui
      frame = simplegui.create_frame("My Frame", 100, 100)
      frame.set_canvas_background("Red")
      frame.start()

*     import simplegui
      frame = simplegui.create_frame("My Frame", 100, 100)
      frame.set_canvas_background("red")
      frame.start()

----
