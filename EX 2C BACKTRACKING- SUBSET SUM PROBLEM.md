# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. Start from index 0 and initialize the current sum as 0.

2. At each step, for the current index:

3. Include the element in the subset and recursively check if the remaining sum can be formed with the rest of the elements.

4. If the current sum equals the target sum → return True (subset found).

5. If current index exceeds the size of the array or current sum exceeds the target → backtrack.

6. If no valid subset is found after exploring all options, return False  

## Program:

Developed by: GANESH R

Register Number:  212222240029

```python
def SubsetSum(a,i,sum,target,n):

# Write your code here
    if i == n:
        return sum == target
    
    # Include the current element in the subset
    if SubsetSum(a, i + 1, sum + a[i], target, n):
        return True
    
    # Exclude the current element from the subset
    if SubsetSum(a, i + 1, sum, target, n):
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



```

## Output:
![image](https://github.com/user-attachments/assets/bbc14861-686a-4f68-8098-a3b129a4bb67)



## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
