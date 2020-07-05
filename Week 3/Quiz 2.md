# Question 1
  When the following code is executed, how many times is `timer_handler` called?  

    import simplegui

    def timer_handler():
       return 0

    timer = simplegui.create_timer(10, timer_handler)
    timer.start()

The body of `timer_handler` isn't given, as it is irrelevant for this question.

### Answer
    Unlimited - It is called repeatedly until you stop the program.  

### Code
      import simplegui
      import time;  # This is required to include time module.

      Count = 0
      def timer_handler():
          global Count, timer
          Count += 1
          print Count
          if Count == 10:
              timer.stop()
              timer = simplegui.create_timer(1000, timer_handler)
              timer.start()

      timer = simplegui.create_timer(10, timer_handler)
      timer.start()

----
# Question 2
  You want a timer to create exactly 1000 events. Which of the following solutions are possible?  

### Answer
    Have a global counter for the number of timer calls. In the timer handler, increment the counter. In the timer handler, check the count and possibly stop the timer.  

### Code
      import simplegui
      import time;  # This is required to include time module.

      Count = 0
      def timer_handler():
          global Count, timer
          Count += 1
          print Count
          if Count == 10:
              timer.stop()
              timer = simplegui.create_timer(1000, timer_handler)
              timer.start()

      timer = simplegui.create_timer(10, timer_handler)
      timer.start()

### Explanation  
* In the timer handler, have a local counter for the number of timer calls. In the timer handler, increment the counter. In the timer handler, check the count and possibly stop the timer. -> With a local counter, you'll forget the count between calls.  
* Specify the number of timer events when creating the timer. -> There is no such option.  
* Have a global counter for the number of timer calls. Outside the timer handler, increment the counter. Outside the timer handler, check the count and possibly stop the timer. -> You can't count the timer calls outside of the handler.

----
# Question 3
  How do you change the frequency of a running timer, either increasing or decreasing the frequency? E.g., in the code below, we want code at the question marks that changes the timer.  

    .
    timer = simplegui.create_timer(1000, timer_handler)
    timer.start()
    .
    ???

### Answer
    You can't. But, you can stop this timer, and start a new one with a different frequency and same handler as given in the code below  

      timer.stop()
      timer = simplegui.create_timer(300, timer_handler)
      timer.start()  

----
# Question 4
  How many timers can you have running at once?  

### Answer
    Unlimited  

----
# Question 5
  The function `time.time()` is used in Python to keep track of time. What unit of time is associated with the value returned by `time.time()`?  

### Answer
    Seconds  

### Explanation
    time.time( ) returns the current time instant, a floating-point number of seconds since the Epoch (12:00am, January 1, 1970).

----
# Question 6
  In Python, the `time` module can be used to determine the current time. This module includes the method `time` which returns the current system time in seconds since a date referred as the Epoch. Write a CodeSkulptor program that experiments with the method `time.time()` and determines what date and time corresponds to the Epoch. Enter the year of the Epoch as a four digit number.  

### Answer
    1970  

### Explanation
        import time
        ticks = time.time()
        print "Number of ticks since 12:00am, January 1, 1970:", ticks

    The above code outputs the returns the current time as the number of seconds since Epoch (12:00am, January 1, 1970).

----
# Question 7
  The Python code below uses a timer to execute the function `update()` 10 times, computing a good approximation to a common mathematical function. Examine the code, and run it while varying the input value `n`. What is the common name for what this computes?  

    # Mystery computation in Python
    # Takes input n and computes output named result

    import simplegui

    # global states
    result = 1
    iteration = 0
    max_iterations = 10

    # helper functions
    def init(start):
        """Initializes n."""
        global n
        n = start
        print "Input is", n

    def get_next(current):
        """???  Part of mystery computation."""
        return 0.5 * (current + n / current)

    # timer callback
    def update():
        """???  Part of mystery computation."""
        global iteration, result
        iteration += 1
        # Stop iterating after max_iterations
        if iteration >= max_iterations:
            timer.stop()
            print "Output is", result
        else:
            result = get_next(result)

    # register event handlers
    timer = simplegui.create_timer(1, update)

    # start program
    init(13)
    timer.start()

### Answer
    Square root of n  

----
# Question 8
  Given any initial natural number, consider the sequence of numbers generated by repeatedly following the rule:  
* divide by two if the number is even or  
* multiply by 3 and add 1 if the number is odd.  

The Collatz conjecture states that this sequence always terminates at 1. For example, the sequence generated by 23 is: 23, 70, 35, 106, 53, 160, 80, 40, 20, 10, 5, 16, 8, 4, 2, 1. Write a Python program that takes a global variable `n` and uses a timer callback to repeatedly apply the rule above to `n`. Run this program for `n` = 217. What is the largest number in the sequence generated by this starting value? To test your code, starting at `n` = 23 generates a sequence with a maximum value of 160.  

### Answer
    726

### Code
    # Takes input n and computes the sequence of numbers generated by repeatedly following the rule:
    # 1) divide by two if the number is even or
    # 2) multiply by 3 and add 1 if the number is odd.

    import simplegui

    # define global variables
    maximum, n = 0, 0

    # helper functions
    def init(start):
        """Initializes n."""
        global n
        n = start
        print "Input is", n

    def get_next(current):
        """???  Part of mystery computation."""
        if current % 2 == 0:
            return current / 2
        else:
            return current * 3 + 1

    # timer callback
    def update():
        """???  Part of mystery computation."""
        global n, maximum
        maximum = max(n, maximum)
        print n
        # Stop iterating if n is 1
        if n == 1:
            timer.stop()
            print "Maximum number was ", maximum
        else:
            n = get_next(n)

    # register event handlers
    timer = simplegui.create_timer(1, update)

    # start program
    init(217)
    timer.start()

----
# Question 9
  CodeSkulptor runs your Python code by converting it into Javascript when you click the "Run" button and then executing this Javascript in your web browser. If the SimpleGUI frame is spawned as a separate window, you should see an animation of an explosion in the canvas for this frame. If the SimpleGUI frame is spawned as a separate tab on top of the existing window containing the code, the animation will "freeze" and a single static image is displayed. As explained in the FAQ, what is the explanation for this behavior?  

### Answer
    To save resources, modern browsers only execute the Javascript associated with the topmost tab of a window. The animation freezes since the code tab and its associated Javascript is no longer the topmost tab.  

----
