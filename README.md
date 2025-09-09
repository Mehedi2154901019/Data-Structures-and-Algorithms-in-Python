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
So, for n iterations the time complexity of the for loop will be **O(n)**

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















