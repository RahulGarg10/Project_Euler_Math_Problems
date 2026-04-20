# Summation of Primes

## Question
<p>The sum of the primes below $10$ is $2 + 3 + 5 + 7 = 17$.</p>
<p>Find the sum of all the primes below or equal to $N$. Problem Links:</p>

**Project Euler:** https://projecteuler.net/problem=10

**Hackerrank:** https://www.hackerrank.com/contests/projecteuler/challenges/euler010/problem?isFullScreen=false

## Solution
I am implementing a **sieve of Eratosthenes** algorithm to find **prime numbers** upto $N$.

**Time Complexity:** $O(n.loglog \ n)$

**Space Complexity:** $O(\frac{1}{2}.n)$

### Project Euler Solution
```python3
n=2000000
number = [2] + [k for k in range(3,n+1,2)]
length = len(number)
num = 3
while(num * num <=  n):
    if number[num//2] != 0 :
        i = (num*num)//2
        while(i<length):        
            number[i] = 0
            i=i+num
    num = num + 2
            
print(sum(number))
```

### Hackerrank Solution

```python3
import sys
def sieve():
    m = 1000000
    number = [2] + [k for k in range(3,m+1,2)]
    length = len(number)
    for num in number:
        if num == 2 or num == 0: 
            continue
        if (num * num >  m):
            break
        if number[num//2] != 0 :
            i = (num*num)//2
            number[i:length:num] = [0]*len(number[i:length:num])
    return number
    
def summation(n):
    sums = 0
    for p in number:
        if p <=n:
            sums = sums + p
        else:
            break  
    return sums
    
number = sieve()
results = []
t = int(input().strip())
for a0 in range(t):
    n = int(input().strip())
    sums = summation(n)
    results.append(str(sums))   
sys.stdout.write("\n".join(results) + "\n")
```

```python3
n=1000000
number = [2] + [k for k in range(3,n+1,2)]
length = len(number)
num = 3
while(num * num <=  n):
    if number[num//2] != 0 :
        i = (num*num)//2
        while(i<length):
            number[i] = 0
            i=i+num
    num = num + 2
            
print(sum(number))

```

Final Solution
```python3

import sys
def sieve():
    m = 1000000
    primes = []
    sums = 0
    prime_sum=[]
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
            sums = sums + num
            prime_sum.append(sums) 
    return primes, prime_sum
    
def summation(n):
    low_pt = 0
    high_pt = len(primes)-1
    if n < primes[-1]:
        while(high_pt - low_pt > 1):
            mid = (low_pt + high_pt) // 2
            if primes[mid] == n:
                result = prime_sum[mid]
                break
            elif primes[mid] > n:
                high_pt = mid
                result = prime_sum[mid-1]
            else:
                low_pt = mid
                result = prime_sum[mid]
    else:
        result = prime_sum[-1] 
    
    return result
    
primes, prime_sum = sieve()
resultants = []
t = int(input().strip())
for a0 in range(t):
    n = int(input().strip())
    sums = summation(n)
    resultants.append(str(sums))   
sys.stdout.write("\n".join(resultants) + "\n")


```
