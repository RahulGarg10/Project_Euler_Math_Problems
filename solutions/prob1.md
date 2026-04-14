
# Multiples of 3 or 5

## Question
If we list all the natural numbers below $10$ that are multiples of $3$ or $5$, we get $3, 5, 6$ and $9$. The sum of these multiples is $23$. Find the sum of all the multiples of $3$ or $5$ below $N$. Problem Links:

**Project Euler:** https://projecteuler.net/problem=1

**Hackerrank:** https://www.hackerrank.com/contests/projecteuler/challenges/euler001/problem?isFullScreen=false

## Solution
Calculate the sum of multiples of 3 + sum of multiples of 5 - sum of multiples of 15. If we use loop to iterate then time complexity is $O(n)$ which increases with n. So we use sum of AP formula which is independents of size N.

**Time Complexity:** $O(1)$

**Space Complexity:** $O(1)$

```python3
n = int(input().strip())
def sum_of_multiples(i):
    multiples_no = (n-1) // i
    return  multiples_no * (2 * i + (multiples_no - 1)*i) // 2
    
sums = sum_of_multiples(3) + sum_of_multiples(5) - sum_of_multiples(15)
print(sums)
```
