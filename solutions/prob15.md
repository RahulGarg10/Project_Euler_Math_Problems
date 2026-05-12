
# Lattice paths

## Question
Problem Links:

**Project Euler:** https://projecteuler.net/problem=15

**Hackerrank:** https://www.hackerrank.com/contests/projecteuler/challenges/euler015/problem?isFullScreen=false

## Solution
Calculate the sum of multiples of 3 + sum of multiples of 5 - sum of multiples of 15. If we use loop to iterate then time complexity is $O(n)$ which increases with n. So we use sum of AP formula which is independents of size N.

**Time Complexity:** $O(1)$

**Space Complexity:** $O(1)$

### Hackerrank Solution

```python3
def factorial(num):
    product=1
    for i in range(1,num+1):
        product = product * i
    return product

MOD = 10**9 + 7

t = int(input().strip())
for a0 in range(t):
    n,m = input().strip().split(' ')
    n,m = [int(n),int(m)]
    
    ways = factorial(n+m)//(factorial(n) * factorial(m))
    
    print(ways % MOD)
```

### Project Euler Solution

```python3
def factorial(num):
    product=1
    for i in range(1,num+1):
        product = product * i
    return product

t = int(input().strip())
for a0 in range(t):
    n,m = input().strip().split(' ')
    n,m = [int(n),int(m)]
    
    ways = factorial(n+m)//(factorial(n) * factorial(m))
    
    print(ways)
```

