# Smallest Multiple

## Question
$2520$ is the smallest number that can be divided by each of the numbers from $1$ to $10$ without any remainder.</p>
<p>What is the smallest positive number that is <strong class="tooltip">evenly divisible<span class="tooltiptext">divisible with no remainder</span></strong> by all of the numbers from $1$ to $N$? Problem Links:

**Project Euler:** https://projecteuler.net/problem=5

**Hackerrank:** https://www.hackerrank.com/contests/projecteuler/challenges/euler005/problem

## Solution
They are essentially asking for lcm

```python3
n=20
lcm = 1
def gcd(a,b):     # GCD is greatest common divisior
    i = 2 
    temp = 1
    while(i<=a and i<=b):
        pow_num = 0
        while a%i==0 and b%i == 0:
            pow_num = pow_num + 1
            a = a // i
            b = b // i
        temp = temp * i**pow_num
        i = i+1
    
    return temp

for i in range(2, n+1):
    lcm = lcm * i // gcd(lcm, i)
    
print(lcm)
```
