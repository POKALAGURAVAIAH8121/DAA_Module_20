# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1.Start with the first element, checking if including it leads to the target sum. 

2.Recursively try both possibilities for each element: include or exclude it.

3.If at the end of the list, check if the current sum equals the target. 

4.Return True if any recursive path leads to the target sum. 

5.Print all input elements and the result, indicating whether a subset was found

## Program:
~~~
Program to implement Subset sum problem.
Developed by: POKALA GURAVAIAH
Register Number:  212222040114

def SubsetSum(a, i, current_sum, target, n):
    if i == n:
        return current_sum == target
    if SubsetSum(a, i + 1, current_sum + a[i], target, n):
        return True
    if SubsetSum(a, i + 1, current_sum, target, n):
        return True
    return False

a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")

~~~
## Output:
<img width="400" alt="image" src="https://github.com/user-attachments/assets/ffe32271-cb12-495d-9fe9-8d5fec39a95c" />

## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
