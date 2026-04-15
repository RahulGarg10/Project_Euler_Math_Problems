
# Largest Palindrome Product

## Question
A palindromic number reads the same both ways. The smallest 6 digit palindrome made from the product of two 3-digit numbers is $101101 = 143 \times 707$.

Find the largest palindrome made from the product of two 3-digit numbers which is less than $N$.
Problem Links:

**Project Euler:** https://projecteuler.net/problem=4

**Hackerrank:** https://www.hackerrank.com/contests/projecteuler/challenges/euler004/problem?isFullScreen=false

## Solution
Both the problems make N a six digit no. The product of two 3-digit no. will have at max 6-digits. In both problems,

**Time Complexity:** $O(1)$

**Space Complexity:** $O(1)$

### Project Euler Problem
```python3
def num_factor(n):
    l = 1
    for k in range(999,99,-1):  # since we are intersted in largest no., so range starts from 999 to reduce no. steps
        if n%k==0:
            l = n // k
        if l > 100 and l < 1000: 
            return True  
    return False

flag = False
for x in range (9,0,-1):
    for y in range (9,-1,-1):
        for z in range(9, -1,-1):
            # 10**5*x + 10**4*y + 10**3*z + 10**2*z + 10*y + x = 11 * (9091*x + 910*y + 100*z)
            num = 11 * (9091*x + 910*y + 100*z)
            # since 11 is prime, so one factor must be multiple of 11 in the solution of this problem
            if num < n:
                flag = num_factor(num)
            if flag:
                print(num)
                break
        if flag:
            break
    if flag:
        break
            
```
### Hackerrank Problem
```python3
def num_factor(n):
    l = 1
    # Here we are finding largest below N, so in worst case scenario, range starts from 100 or 999 doesn't matter.
    # But in all cases range from 999 to 99 do better by ~50-900 steps in final tally which is ignorable. 
    for k in range(100,1000):
        if n%k==0:
            l = n // k
        if l > 100 and l < 1000: 
            return True  
    return False

flag = False
for x in range (9,0,-1):
    for y in range (9,-1,-1):
        for z in range(9, -1,-1):
            # 10**5*x + 10**4*y + 10**3*z + 10**2*z + 10*y + x = 11 * (9091*x + 910*y + 100*z)
            num = 11 * (9091*x + 910*y + 100*z)
            # since 11 is prime, so one factor must be multiple of 11 in the solution of this problem
            if num < n:
                flag = num_factor(num)
            if flag:
                print(num)
                break
        if flag:
            break
    if flag:
        break
    
            
```
