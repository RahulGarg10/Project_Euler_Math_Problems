
# Largest Prime Factor

## Question
<p>The prime factors of $13195$ are $5, 7, 13$ and $29$.</p>
<p>What is the largest prime factor of the number $N$?</p>

Problem Links:

**Project Euler:** https://projecteuler.net/problem=3

**Hackerrank:** https://www.hackerrank.com/contests/projecteuler/challenges/euler003/problem?isFullScreen=false

## Solution
The solution is for n > 1. In function **factor** we are constantly dividing by same no. k because we are interested in only prime numbers. For ex if n = 27, then its factors are 3 and 9. But we want only 3 because its prime and later we do not want to check for div = 9 (div = div + 2).

**Time Complexity:** $O(\sqrt{\mathstrut n})$

**Space Complexity:** $O(1)$

```python3
n = int(input().strip())
large_factor = 2
div = 3
def factor(n, k):
    while(n % k == 0):         
        n = n // k
    return n, k
    
n,large_factor = factor(n, 2)  # dividing by 2, untill all multiples 2 as factor of n is removed 

while(div * div <= n):         # Since number is now odd, we start from 3 and incrementing it by 2.
    n,large_factor = factor(n, div)
    div = div + 2     


if n > 2 :                     # This means n itself is a prime number
    large_factor = n 
print(large_factor)
            
```
