# Question 1
  What Python operator takes two strings and forms the combination of these two strings, one followed by the other.

### Answer
    +

----
# Question 2
  What does the draw handler parameter represent?  

### Answer
    The canvas  

----
# Question 3
  What happens if you draw text outside the canvas coordinates?  

### Answer
Some or none of the text is shown. Conceptually, the text is drawn at whatever coordinates are given, but only whatever text fits within the canvas coordinates is shown.  

----
# Question 4
  Assume we have a canvas that is 200 pixels wide and 300 pixels high. We want to draw a green line between the upper left corner and the lower right corner. Which of the following calls will accomplish this?  

### Answer
    canvas.draw_line((199, 299), (0, 0), 10, "Green")

----
# Question 5
  Consider the following function definition.  

    def date(month, day):
        """
        Given numbers month and day, returns a string of the form '2/12',
        with the month followed by the day.
        """
        return month + "/" + day

    print date(2, 12)

  This definition leads to an error. To fix it, what Python expression should replace the question marks below?  

    def date(month, day):
        """
        Given numbers month and day, returns a string of the form '2/12',
        with the month followed by the day.
        """
        return ???

    print date(2, 12)  

### Answer
    str(month) + "/" + str(day)  

----
# Question 6
  Assume we have a variable `word` that contains a string, such as `"Mississippi"` or `"indivisible"`. We would like to determine how many "**i**"'s are in the string `word`. What code should replace the question marks in the following function definition?

    def number_of_i(word):
        """Returns the number of lower-case i's in the word."""
        return ???

### Answer
    word.count("i")  

----
# Question 7
  Where should your `draw_text`, `draw_line`, and similar drawing calls be?  

### Answer
    In a draw handler, or a helper function called from it.  

----
# Question 8
  Which of the following function calls are valid, i.e., don't lead to an error?  

### Answer
* `int("5")`
* `float("5")`

----
# Question 9
  Turn the following description into a CodeSkulptor program, and run it.  
  1) Create a 300-by-300 canvas.  
  2) Draw two circles with radius 20 and white lines of width 10. One is centered at (90,200) and one at (210,200).  
  3) Draw a red line of width 40 from (50,180) to (250,180).  
  4) Draw two red lines of width 5 from (55,170) to (90,120) and from (90,120) to (130,120).  
  5) Draw a red line of width 140 from (180,108) to (180,160).  

  The resulting picture is a simple diagram of what?  

### Answer
    An automobile  

----
# Question 10
  To draw a diagram of an archery target in CodeSkulptor, we can put a small yellow circle with a black border on top of a slightly bigger yellow circle with a black border, on top of a big white circle with a black border. In what order should your code draw these circles?  

### Answer  
    Largest first  

### Explanation  
    Whatever you draw last appears to be on top.

----
