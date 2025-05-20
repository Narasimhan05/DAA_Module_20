# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.

## Algorithm
1. Input Array & Target Sum: Get the size of the array, then populate it with integer values, and finally get the target sum s.
2. Generate Subsets: Iterate through all possible subset sizes from 0 to n (the length of the array).
3. Create Combinations: For each subset size, use itertools.combinations to generate all unique combinations of elements from the input array.
4. Check Sum: For each generated subset, calculate its sum.
5. Count Matches: If the subset's sum equals the target sum s, increment a counter and return the final count.

## Program:
Developed by: NARASIMHAN S 
Register Number: 212223230133- 

```
from itertools import combinations
def subsetSum(arr, n, i,s, count):
    for i in range(n):
        for subset in combinations(arr,i):
            if sum(subset)==s:
                count+=1
    return count

arr=[]
size=int(input())
for j in range(size):
    value=int(input())
    arr.append(value)
s = int(input())
n = len(arr)
 
print(subsetSum(arr, n, 0, s, 0))
```

## Output:
![image](https://github.com/user-attachments/assets/db58fa01-adc6-4824-a694-d9fecce1104a)

## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
