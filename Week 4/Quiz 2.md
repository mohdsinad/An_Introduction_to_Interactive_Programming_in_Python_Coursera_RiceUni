# Question 1
  In Python, `[1, 2, 3]` is of type list. What is the name of the type of `(1, 2, 3)`?  

### Answer
    Tuple    

----
# Question 2
  Which of the following types of data are immutable in Python?  

### Answer
    Numbers  
    Strings  
    Booleans  
    Tuples    

----
# Question 3
  Which of the following functions must include a global `point` declaration in order to change the global variable `point`?  

    point = [0, 0]  

    def function1():  
      point[0] += 1  
      point[1] += 2  

    def function2():  
      point = [50, 50]  

### Answer
    function2  

----  
# Question 4
  Consider the following program.  

    x = range(5)  
    ???  
    ???  

  We can replace the question marks with what two statements to make both variables have the value `[0, 1, 10, 3, 4]`?    

### Answer
    1) y = x
       x[2] = 10  

    2) y = x
       y[-3] = 10  

### Code
    x1 = range(5)
    y1 = x1
    x1 = [0, 1, 10, 3, 4]
    print x1, y1

    x2 = range(5)
    y2 = x2
    x2[2] = 10
    print x2, y2

    x3 = range(5)
    y3 = x3
    y3 = [0, 1, 10, 3, 4]
    print x3, y3

    x4 = range(5)
    x4 = y4
    x4[2] = 10
    print x4, y4

    x5 = range(5)
    y5 = x5
    y5[-3] = 10
    print x5, y5

    x6 = range(5)
    y6[-3] = 10
    x6 = y6
    print x6, y6  

----
# Question 5
  In our program, the variable `position` represents a 2D position on the canvas. We want to be able to change the position by some amount in variable `delta`. Why is the following code snippet incorrect?  

    position = [50, 50]  
    delta = [1, -2]  
    ...  
    position = position + delta  

### Answer
    The + operator on lists does not mean addition of the numbers in a list.  

----
# Question 6
  Consider the following program.  

    a = ["green", "blue", "white", "black"]  
    b = a  
    c = list(a)  
    d = c  
    a[3] = "red"  
    c[2] = a[1]  
    b = a[1 : 3]  
    b[1] = c[2]  

  At the end of this code, to how many list objects do the variables refer?

### Answer
    3  

### Explanation
    At the end print a, b, c, d and notice the changes. Run the code in Viz mode.

----
# Question 7
  Convert the following specification into code. Do the point and rectangle ever overlap? A point starts at `[10, 20]`. It repeatedly changes position by `[3, 0.7]` - e.g., under button or timer control. Meanwhile, a rectangle stays in place. Its corners are at `[50, 50]` (upper left), `[180, 50]` (upper right), `[180, 140]` (lower right), and `[50, 140]` (lower left).    

### Answer
    Yes  

### Code
    import simplegui

    # Initialize globals
    WIDTH = 400
    HEIGHT = 300
    pos = [10, 20]
    vel = [3, 0.7]

    # define event handlers
    def draw(canvas):

        # Update point position
        pos[0] += vel[0]
        pos[1] += vel[1]

        # Draw point
        canvas.draw_point(pos, 'White')
        canvas.draw_polygon([[50, 50], [180, 50], [180, 140], [50, 140]], 1, 'Yellow', 'Orange')

    # create frame
    frame = simplegui.create_frame("Point physics", WIDTH, HEIGHT)

    # register event handlers
    frame.set_draw_handler(draw)

    # start frame
    frame.start()

----
# Question 8
  Assume we are using acceleration control for a spaceship in a game. That is, we regularly have the following updates:  

* The position is incremented by the time interval multiplied by the velocity. This happens on each draw event.  
* The velocity is incremented by the time interval multiplied by the acceleration. This happens on each draw event.  
* The acceleration is periodically incremented by some fixed vector (the same vector for each step). This could happen on keyboard or timer events.  

Assume that, initially, the ship is stationary and subject to no acceleration. What sort of trajectory will the spaceship fly in?  

### Answer
    Straight line

### Explanation
    Since the change to acceleration is a fixed constant, the velocity will always be in the direction indicated by this constant.

### Code
    import simplegui

    # Initialize globals
    WIDTH = 600
    HEIGHT = 400
    pos = [0, 0]
    vel = [0.1, 0.07]
    acc = [0, 0.01]

    # define event handlers
    def draw(canvas):

      # Update point position
      pos[0] += vel[0]
      pos[1] += vel[1]

      # Update point velocity
      vel[0] += acc[0]
      vel[1] += acc[1]

      # Draw ball
      canvas.draw_circle(pos, 10, 5, 'Yellow', 'Orange')

    def key_handler(key):
      if key == simplegui.KEY_MAP["a"]:
          acc[0] += 0.01
          acc[1] += 0.02       

    # create frame
    frame = simplegui.create_frame("Point physics", WIDTH, HEIGHT)

    # register event handlers
    frame.set_draw_handler(draw)
    frame.set_keydown_handler(key_handler)

    # start frame
    frame.start()

----
# Question 9
  Write a Python program that initializes a global variable to 5. The keydown event handler updates this global variable by doubling it, while the keyup event handler updates it by decrementing it by 3. What is the value of the global variable after 12 separate key presses, i.e., pressing and releasing one key at a time, and repeating this 12 times in total? To test your code, the global variable's value should be 35 after 4 key presses.    

### Answer
    8195  

### Code
    import simplegui

    # initialize state variables
    count = 0
    value = 5

    # event handlers
    def keydown(key):
        global count, value
        count += 1
        value `*`= 2
    def keyup(key):
        global value
        value -= 3
    def draw(c):
        c.draw_text(str(value), [10, 25], 20, "Red")
        c.draw_text(str(count), [100, 25], 20, "Yellow")

    # create frame             
    f = simplegui.create_frame("Output", 130, 35)

    # register event handlers
    f.set_keydown_handler(keydown)
    f.set_keyup_handler(keyup)
    f.set_draw_handler(draw)

    # start frame
    f.start()

----
