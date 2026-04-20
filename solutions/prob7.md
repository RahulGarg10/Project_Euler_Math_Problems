
# 10 001st Prime

## Question
By listing the first six prime numbers: $2, 3, 5, 7, 11, and \ 13$, we can see that the $6th$ prime is $13$.
What is the $10, \ 001st$ prime number or if generalised, what is $N^{th}$ prime number?
Problem Links:

**Project Euler:** https://projecteuler.net/problem=7

**Hackerrank:** https://www.hackerrank.com/contests/projecteuler/challenges/euler007/problem?isFullScreen=false

## Solution
I am implementing a **sieve of Eratosthenes** algorithm to find **prime numbers** upto $N$.

**Time Complexity:** $O(m.loglog \ m)$

**Space Complexity:** $O(\frac{1}{2}.m)$

Where m = 100000

```python3
import sys
def sieve(m):
    primes = []
    number = [2] + [k for k in range(3,m+1,2)]
    length = len(number)
    for num in number:
        if num == 2 or num == 0: 
            continue
        if (num * num > m):
            break
        if number[num//2] != 0 :
            i = (num*num)//2
            number[i:length:num] = [0]*len(number[i:length:num])
    for num in number:
        if num:
            primes.append(num)
    return primes
m = 100000    
primes = sieve(m)
resultants = []
t = int(input().strip())
for a0 in range(t):
    n = int(input().strip())
    while n>=len(primes):
        m = m + 100000
        primes = sieve(m)
    if n<len(primes):
        result = primes[n-1]
    
    resultants.append(str(result))   
sys.stdout.write("\n".join(resultants) + "\n")

```
