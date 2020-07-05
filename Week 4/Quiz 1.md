# Question 1
  What built-in function will add all the numbers in a list of numbers?

### Answer
    sum  
----
# Question 2
  Let `my_list` be the list `["This", "course", "is", "great"]`.
* What is `len(my_list)`?
* What non-negative number is the index of `"great"`?  

### Answer
    4 3  

----
# Question 3
  Let `my_list` be the list `["This", "course", "is", "great"]`. What non-negative numbers can be used to get the slice `["course", "is"]`? i.e., what two non-negative numbers should we put in `my_list[??? : ???]` to get that result?

### Answer
    1 3  

----
# Question 4
  If we want to split a list `my_list` into two halves, which of the following uses slices to do so correctly? More precisely, if the length of `my_list` is 2n, i.e., even, then the two parts should each have length n. If its length is 2n+1, i.e., odd, then the two parts should have lengths n and n+1.  

### Answer
    my_list[0 : len(my_list) // 2] and my_list[len(my_list) // 2 : len(my_list)]
    my_list[: len(my_list) // 2] and my_list[len(my_list) // 2 :]  

### Explanation
`my_list[0 : len(my_list) // 2]` and `my_list[len(my_list) // 2 + 1 : len(my_list)]` : The list element at index `len(my_list) // 2` is not in either part.  

`my_list[: len(my_list) // 2 - 1]` and `my_list[len(my_list) // 2 :]` : The list element at index `len(my_list) // 2 - 1` is not in either part.  

----
# Question 5
  What is the distance between point `[4, 7]` and the nearest point on the circle centered at `[2, 9]` with radius 2?

### Answer
    0.82842712475  

### Explanation
    import math
    point1 = [4, 7]
    point2 = [2, 9]
    distance = math.sqrt(((point2[0]-point1[0])^2) + ((point2[1]-point1[1])^2))
    print distance

----
# Question 6
  A ball with velocity `[4, 2]` reflects off a vertical wall. What is its new velocity?  

### Answer
    [-4, 2]  

### Explanation
    On collision with a vertical wall only the X component of velocity changes, i.e. it becomes negative.

----
# Question 7
  Which of the following illustrate how to properly structure a keydown or keyup event handler?

### Answer
    def keydown_handler(key):  
      if key == simplegui.KEY_MAP["left"]:  
      ...    

----
# Question 8
  Assume you have a program with a keydown handler. You run it, and press a single key and hold it down continuously. How many times does the keydown handler get called?  

### Answer
    1

----  
# Question 9
  Several keys on the keyboard, such as Shift, CapsLock, and Ctrl, typically act to modify what happens when you press other keys, rather than doing anything on their own. When using the SimpleGUI keydown handler, how are such keys treated?  

### Answer
    Independent key press events - e.g., pressing Shift by itself creates an event.  

### Explanation
    Shift gives the value 16, Control key gives the value of 17, etc.

----
