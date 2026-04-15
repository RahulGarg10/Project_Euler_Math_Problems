
# Sum Square Difference

## Question
The sum of the squares of the first ten natural numbers is,

$$1^2 + 2^2 + ... + 10^2 = 385.$$
The square of the sum of the first ten natural numbers is,
$$(1 + 2 + ... + 10)^2 = 55^2 = 3025.$$
Hence the difference between the sum of the squares of the first ten natural numbers and the square of the sum is $3025 - 385 = 2640$.

Find the difference between the sum of the squares of the first $N$ natural numbers and the square of the sum.

Problem Links:

**Project Euler:** https://projecteuler.net/problem=6

**Hackerrank:** https://www.hackerrank.com/contests/projecteuler/challenges/euler006/problem?isFullScreen=false

## Solution
Using formulae,

$$1^2 + 2^2 + 3^2 + ... + n^2 =  \frac{n.(n + 1)(2n + 1)}{6}$$

$$1 + 2 + ... + n = \frac{n.(n + 1)}{2}$$

**Time Complexity:** $O(1)$

**Space Complexity:** $O(1)$

```python3
n = int(input())
simp_sum = n * (n + 1) // 2
sqr_sum = (n * (n + 1) * (2 * n + 1)) // 6
l = simp_sum**2
if l > sqr_sum:
    print(l - sqr_sum)
else: 
    print(sqr_sum - l)

        
```
