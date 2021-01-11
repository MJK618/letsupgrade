# Question 1

  Write a program to print the following pattern  
    
    1
    2*2
    3*3*3
    4*4*4*4
    
    ### CODE FOR PATTERN
    for i in range(1,5):
      for k in range(1, i+1):
        if(k>1 and k<=i):
          print("*",end='')
        print(i,end='')
        if(i==k):
          print()
    
# Question 2

  Write a program to print the following pattern

    1
    01
    101
    0101
    10101    
     
    ### CODE FOR PATTERN
    for i in range(6):
	    for j in range(i):
		    print((i+j)%2,end='')
	  print()
    
    
# Question 3

Write the similarity and difference between an array name and a pointer variable.

A. An array is a collection of elements of similar data type and on the otherhand a pointer is a variable that stores the address of other variable. An array size decides the number of variables it can store however a pointer variable can store the address of only one variable in it.
