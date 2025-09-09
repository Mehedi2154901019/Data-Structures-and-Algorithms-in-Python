# Data-Structures-and-Algorithms-in-Python
Data Structure is how your program or data are structured differently for different problems. It is the bricks, rods, or cements for building a complete house. 

# Big O Notation
It is the measurement of time complexity or space complexity of a specific program.  
Note: We take the worst case scenerio for measuring the complexity  
##Time Complexity:
```
x=a+b*10
y=a+b*10000000
```
Here, no matter how big the numbers or calculations are, there is only single line operation.  
So, the time complexity will always be constant. Hence, Time complexity is  **O(1)** for both x and y  

```
for loop
```
This loop depends on the iteration. If there are 5 iterations, complexity will be O(5) and if 10 then O(10)  
So, for n iterations the time complexity of the for loop will be ** O(n) **  

```
for
  for  #nested for loop
```
The nested loop has two for loops. So combining the complexity of those two loops, the time complexity for this program will be **O(n^2)**

```
for
  for #nested for loop

for #another separate for loop
```
Here if we create an equation, it will be like y=an^2+an+b  
We should always take the most influential one, many people say it will be O(n^2+n) but actually the complexity is still O(n^2) as n^2 is the greatest term here.

## Space Complexity
To calculate the space a program will take for execution

```
[4,11,54,63,69,84,97] # simple search from 4 to 97 to find 84
```
This simple seach will start from 4 and go to n th element for worst case scenerio. So to store in memory it will need n units of memory.   
Hence, the space complexity for above problem will be **O(n)**

```
[4,11,54,63,69,84,97,100,102] #Binary search to find 100
```
This will find the middle value 69, compare with 100 and it is greater. So the smaller values or left part with 69 is discarded. Complexity is n/2  
Then again middle value now is 97, it will compare with 100 and again discard left part along with 97. Now n/2^2  
Now the middle value is 100 and it will be the searched value.   
Thus for k iterations,   
k=n/2^k  
1= n/2^k (as worst case scenerio)  
n=2^k  
logn=k  
So, the space complexity for the binary search problem is O(logn)  

# Array
In Java or C++ you need to specify the fixed array type as the array contains only simiral type of elements like:
```
[1,3,4,5,6,3] #only numbers
['cat','bat','rat'] #only strings
```
But python can have multiple types of objects which we call 'List' and we do not need any static declaration of array types in python.
```
['Hello', 3.45,1,'c',{"Sunday_Sales": 45000}, 2544] #different types of data in single list
```
# LinkedList
Arrays have few issues, if we want to insert or delete any value it have to shift all the memory addresses to make or gaph the space for the new value or deletion.  
Also when the memory allocation for the specific array or list is filled, for the new value it has to create more memory addresses along with the original memory size to duplicate the whole array or list to the new place.  
Here comes LinkedList which uses value + address of next value. So while inserting, the next address of previous value is linked to the new value,  
and the next of new value is just pointed towards the value that the previous value was addressing as the next value.
```
1 | 0*523412 -> 2 | 0*523473 -> 3 | null #before inserting
1 | 0*523490 -> 145 | 0*523412 -> 2 | 0*523473 -> 3 | null #after inserting
```
Here, for inserting 145, the next of 1 is pointed to address of 145 and the next of 145 is now addressed to address of 2.   
Thus, no memory wastage, very simple and efficient method.

















