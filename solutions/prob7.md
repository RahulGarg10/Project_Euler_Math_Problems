
# 10 001st Prime

## Question
By listing the first six prime numbers: $2, 3, 5, 7, 11, and \ 13$, we can see that the $6th$ prime is $13$.
What is the $10, \ 001st$ prime number?

 Problem Links:

**Project Euler:** https://projecteuler.net/problem=7

**Hackerrank:** https://www.hackerrank.com/contests/projecteuler/challenges/euler007/problem?isFullScreen=false

## Solution

**Time Complexity:** $O(\log \ n)$

**Space Complexity:** $O(1)$

```python3
n = int(input().strip())
first = 1
second = 2
sums = 0
result = 2
while(sums < n):
    if sums % 2 == 0:
        result = result + sums
    sums = first + second
    first = second
    second = sums
    
print(result)
```
