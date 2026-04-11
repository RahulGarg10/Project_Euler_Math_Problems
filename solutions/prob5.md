# Smallest Multiple

## Question
$2520$ is the smallest number that can be divided by each of the numbers from $1$ to $10$ without any remainder.</p>
<p>What is the smallest positive number that is <strong class="tooltip">evenly divisible<span class="tooltiptext">divisible with no remainder</span></strong> by all of the numbers from $1$ to $N$?
## Solution

```python3
n=20
lcm = 1
def gcd(a,b):
    i = 2 
    temp = 1
    in_loop = 0
    out_loop = 0
    while(i<=a and i<=b):
        pow_num = 0
        out_loop = out_loop +1
        while a%i==0 and b%i == 0:
            in_loop =   in_loop + 1
            pow_num = pow_num + 1
            a = a // i
            b = b // i
        temp = temp * i**pow_num
        i = i+1
    
    print(out_loop," ", in_loop)
    return temp

for i in range(2, n+1):
    lcm = lcm * i // gcd(lcm, i)
    

print(i, " ",lcm)
```
