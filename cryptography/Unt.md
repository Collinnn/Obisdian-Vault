Problem Sheet 9 
[[problem-sheet-9.pdf]] 
# Exercise 1 
## opg 1
$p=31,g=11,h=5$ 
| a | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |10 |
| --------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | -- | 
| $11^{a}\text{ mod }31$ | 11 | 28 | 29 | 9 | 6 | 4 | 13 | 19 | 23 | 5 | 

Answer is: $a=10$ the worst case would be $|\phi(p)|$ ie 30 
## opg 2 using Lagrange's Theory
we know $g^{p - 1} = 1 \mod p$ since $g \in Z^*_p$ and $p$ is prime ie $\phi(p) = p-1$ we can there for easily evaulate $(g^\frac{p-1}{2})^\alpha = 1 \mod p$ to be true for $\alpha = 2$ using the power product rule
extrapolating this we get the order of 
$g^x$ to $2$ 
$g^y$ to $3$ 
$g^z$ to $5$ 
## opg 3
solving the discreet logarithm of $h^x$ for base $g^x$ mod $p$ 
gives $0$
for $h^y$ with base $g^y$ we get $1$
and for $h^z$ with base $g^z$ we get $0$

from which we now can write the equations: 
$x \equiv 0 \mod 2$ 
$x \equiv 1 \mod 3$ 
$x \equiv 0 \mod 5$
using CRT we can now calculate x as 
$x = a_1 \cdot N_1 \cdot N_1' + a_2 \cdot N_2 \cdot N_2' + a_3 \cdot N_3 \cdot N_3'$ 

since $a_1, a_3 = 0$ and $a_2 = 1$ 
$x = N_2 \cdot N_2'$ 
$N_2 = \frac{p-1}{3} = 10$
$N_2' = N_2^{-1} \mod 3 =>$
$N_2' = 1^{-1} \mod 3$ 
$\equiv N_2' = 1$ 

We can there for calculate $x = 10 \cdot 1 = 10$ letting us calculate the descrite logorithm $a$ using only 4 multiplications modulo
## opg 4
Worst case would be having to calculate $B$ amounts of multiplications modulo $l$ amount of times 
# Exercise 3 
## opg 1 
Using the exponential product rule $(g^a)^b = (g^b)^a$ 
Bob can know if the message is $0$ by checking if $(c_1)^b = c_2\mod p$ Re-Exam 2022 [[Re-Exam2022]] 

## Part 1 
### 1. 
use Maple 
### 2. 
A: False we don't encrypt the public key B: True, ECB is the simplest Block Cipher C: False, we want Key length Large D: False E: F: not pensum G: False 
### 3. 

### 4.
## Part 2. 
### 5. find the prime factors of 91
  $7^1$ $13^1$ $(7-1)(13-1) = 72$ 
### 6. 
  $2^d$ 
## Part 3. 
### 7. 
### 8. 
### 9.
50 in binary is 110010 $4^2 \cdot 4 = 1 \mod 7$ $1^2 = 1 \mod 7$ $1^2 = 1 \mod 7$ $1^2 \cdot 4 = 4 \mod 7$ $4^2 = 2 \mod 7$ 
### 10. 
(a) $c = 100^5 \mod 9999999983 = 17$ 
(b) 2 
(c) since $2^5$ is 32 
### 11. 
### 12. 
(a) 5 in binary is 101 $10^2 = 30 \mod 35$ $30^2 \cdot 10 = 5 \mod 35$ 
(b) $2^5 = 32 
### 13. 
$A = g^a = 3^4 = 81 = 13 \mod 17$ $B = g^b = 3^7 = 13 \cdot 10= 11 \mod 17$ $k = B^a = 11^4 = 4 \mod 17$
