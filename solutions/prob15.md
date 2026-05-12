
# Lattice paths

## Question
Problem Links:

**Project Euler:** https://projecteuler.net/problem=15

**Hackerrank:** https://www.hackerrank.com/contests/projecteuler/challenges/euler015/problem?isFullScreen=false

## Solution
If moving from top-left corner to bottom-right corner in a $N \times M$ grid, then N and M can be assumed as the no. of steps taken to reach end in N right steps and M down steps. Total steps taken each time is $N+M$. So to arrange the N steps of one kind and M steps of one other kind, total ways is:

$$\text{Total Ways} = \frac{(N+M)!}{(N)! . (M!)}$$

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

