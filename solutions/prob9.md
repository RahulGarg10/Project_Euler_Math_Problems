
#  Special Pythagorean triplet

## Question
A Pythagorean triplet is a set of three natural numbers, $a \lt b \lt c$, for which,
  
$$a^2 + b^2 = c^2$$

<p>For example, $3^2 + 4^2 = 9 + 16 = 25 = 5^2$</p>
<p>Given $N$, Check if there exists any Pythagorean triplet for which, $a + b + c = N$.<br>Find the product $abc$.</p>

Problem Links:

**Project Euler:** https://projecteuler.net/problem=9

**Hackerrank:** https://www.hackerrank.com/contests/projecteuler/challenges/euler009/problem?isFullScreen=false

## Solution

**Time Complexity:** $O(1)$

**Space Complexity:** $O(1)$

```python3
t = int(input().strip())
for a0 in range(t):
    n = int(input().strip())
    product = -1
    large = -1
    for a in range(1, n):
        b = n*(n - 2 * a)/((n - a)*2)
        if b<1:
            continue
        if b / int(b) == 1 and 0<b<n:
            c = n-a-b
            product = a*b*c
        if product > large:
            large = int(product)
    print(large)
```
