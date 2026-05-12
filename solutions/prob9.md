
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
n = int(input().strip())
def sum_of_multiples(i):
    multiples_no = (n-1) // i
    return  multiples_no * (2 * i + (multiples_no - 1)*i) // 2
    
sums = sum_of_multiples(3) + sum_of_multiples(5) - sum_of_multiples(15)
print(sums)
```
