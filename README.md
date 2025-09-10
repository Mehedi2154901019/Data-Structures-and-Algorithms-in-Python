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

# Hash Table or Hash Map
Basically you can think it like a key value pair where you can call the key and it will automatically provide you the value to the corresponding key.  
In Java it is known as HashMap, in C++ std::map and different languages have different syntax.  
In Python, 'Dictionary' is the representation of Hash Map.  
```
dict={
"day 1" : 10,
"day 2" : 11,
"day 3" : 12
}

print(dict["day 1"])
```
The keys are day 1, day 2 and day 3 and 10,11,12 are their values.

### Internal workflow of dictionary in python or hash map
In array or list we have numerical index from 0 to n.     
The main difference is in dictionary, the indices are strings. They are like array or list but the index here is not numerical.   
Suppose, your dictionary size is 5. You want to set the memory address for the key "day 1".  
Now, all the (ASCII value of d+a+y+ +1) MOD 5 = The address where the value for that 'day 1' key will be stored.  
So, to retrieve the value you just call the 'day 1', it will calculate the value in the above method and return you the value for that key.  
```
(Sum of ASCII value of all characters in key) MOD (dictionary size) -> store the value for that key
```
There maybe several other hash functions. This was just one of the examples of how hash maps store the values internally in memory.  
The complexity is O(1) here as the calcualtion is constant.  

### Collision problem of Hash map
Sometimes the MOD might provide same memory address for different keys.  
Assume the key1 MOD size = 7 and key2 MOD size = 7 too. How will it store the value of the second key in the same address?  
There are two popular options: Chaining and Linear probing.  

Chaining: The value of key2 will be stored in the same memory address through a linkedlist.  
Suppose, in the address 7, key1 | value -> key2 | value   
Thus if there is value at the same address for different keys, the solution is to store them as a linkedlist in that memory.  

Linear Probing: If there is collision problem, in this approach the key-value pair will find the following address to store the value.   
If the following address is full, it will find to store in the next address.   
Thus if the last allocated address for that dictionary is also full, it will then start finding the very top address, and so on. finally it will get a place and store the value there. You might think it like a loop where you start from anywhere in the middle, go to the following, if all are filled up, go back to very top, then go to the following, you will get a place somewhere.

# Stack
It is a very simple data structure used by LIFO (Last In First Out) method which stacks a number of data or value like a pile one on another.  
Imagine when you perform any task on computer, if you want to undo any task or update, you type ctrl+z. This is one kind of stack which pops up the latest value.  
Another example might be while browsing a website, you click on the back arrow to go the previous pages. This is also implementation of stack.  

Now, in python stack can be implemented as "list"
```
x=[]
x.append(10) #first data
x.append(20)
x.append(30) #top data

x.pop() # returns 30 as it is the last value and first to come out (LIFO)
```
While list is mostly used, the more efficient way to implement stack in python is 'deque' which can be imported as 'from collection import deque'. However for convenience only list is discussed here.  

# Queue
Queue follows FIFO (First In First Out) like a real life queue at ticket counter where the first person will get the ticket first. Similarly the first data will be accessed first.  
In python, Queue can also be implemented by list. Like Stack, Queue can also be efficiently used by appendleft of deque of collections in python but list is handy.

# Tree
We know tree has parent node, children nodes, levels, neighbors etc. For implementing tree in python, there is no special way just as in Java or C++ where tree is manually implemented with traditional and few OOP concepts.

With the above concepts of Data Structures, the algorithms like sorting, searching etc can be implemented in python which is better approach specially in context of syntax for python rather than Java or C++.   Nevetheless, the comfort depends upon the programmers' hands on specific languages but in this repository the ways of implementation of DSA for Python is discussed.












