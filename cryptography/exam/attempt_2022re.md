# attempt_2022re

## Part 1

### 1 - 100%

**A. 6^2 mod 10= 6**
B. 4^(-1) mod 43 =11
C. 4 mod 11 = 4
**D. 11^2 mod 8 =1**
E. 4*7 mod 29 = 28
F. 8^17 mod 14 = 8

### 2 - 50% i guess
A. **False**, it is used for block ciphers, 
B. **True**, ECB mode is dangerous to use, CTR is modern
C. **False**
D. **False**, CBC is more secure
E. **False**
F. **True**
G. **False**, different key sizes are accepted, but not block lengths

### 3 - 66%
A. **True** i guess, $m^{e}= c \text{ mod } N$ 
B. **False**
C. **True**
D. **False**
E. **False**
F. **True**
G. **False**

### 4 - 100%
A. **False**, only probably
B. **True**,
C. **True**
D. **False**

## Part 2
5. **F = 72** - 100%
6. **B**

## Part 3
### 7
#### a
**Encryption** using rCBC is as follows:
$c_{i}=m_{i-1} \oplus e_{k}(m_{i})$

First apply the encryption function to the message, then xor with previous block


**Decryption** using rCBC is as follows:
$m_{i}=d_{k}(c_{i}\oplus m_{i-1})$

First xor with previous block, then apply decryption 


#### b
??

#### c - 100%
Any message that contains some padding would reveal the length of the message in ECB mode, as the second block would have some structure to it. This makes it vulnerable to frequency analysis

rCBC mode does not reveal this information

### 8 
![[Pasted image 20230514214612.png]]

### 9
50 in binary = 110010

**1**10010 = $4$
1**1**0010 = $(4)^{2}*4$
11**0**010 = $((4)^{2}*4)^2$
110**0**10 = $(((4)^{2}*4)^2)^2$
1100**1**0 = $((((4)^{2}*4)^2)^2)^2*4$
11001**0** = $(((((4)^2*4)^2)^2)^2*4)^2$

### 10
#### a

$N=9999999983$
$e=5$
$m=100$

Encrypt:
$c=m^{e} \text{ mod } N$
$c=100^{5} \text{ mod } 9999999983 = 17$ 

#### b
m=2, c=32

Because $e$ is so small, $m^{e}<N$ very often, resulting in no modulus. 

#### c
![[Pasted image 20230514214821.png]]


#### d
By hashing the message as in RSA-OAEP before applying the RSA encryption, ensures that the messages are randomized

### 11
#### a
the two scenarios where $x$ and $h(y)$ are the same, will "collide"


#### b



### 12
#### a
$m= \sigma^{e} = 10^{5} = 5  \text{ mod } 35$

#### b
$m=2$, see Problem 10b

### 13
![[Pasted image 20230514214234.png]]

### 14
![[Pasted image 20230514215129.png]]
![[Pasted image 20230514215134.png]]