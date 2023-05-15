# attempt_2022

## Part 1

### 1
A. True
B. True
C. False
D. False
E. True
F. False

### 2
A. False
B. False
C. True
D. True
E. False
F. False
G. True

### 3
A. False
B. True
C. False
D. False
E. True
F. False
G. True

### 4
A. True
B. False
C. False
D. True


## Part 2
### 5
how many elements does $\mathbb{Z}^{*}_{55}$ have?
" How many numbers below 55 have $gcd(x,55) = 1$", see [[Euler's Theorem]]

```rust
fn gcd(mut n: u64, mut m: u64) -%3E u64 {
	assert!(n != 0 && m != 0);
	while m != 0 {
		if m %3C n {
			std::mem::swap(&mut m, &mut n);
		}
		m %= n;
	}
	n
}

let mut x = 0;
for i in 1..55 {
	if gcd(55, i) == 1 {
		println!("{} is coprime", i);
		x += 1;
	}
}
println!("x = {}", x);>)

```

**D. 40**



### 6
**E.** $2^{256}/2$ 

## Part 3
### 7
a)
Lack of confidentiality
The same input block always generates the same output block. This is not secure as messages often can start/end with the same sequence

b)
Lack of integrity
Each input block is encrypted independently an attacker can modify or reorder the ciphertext blocks without affecting the decryption process


c)
CTR is not vulnerable to the attack in a) since each block is XOR'd with a string of letters that vary based on position in the message
CTR is not vulnerable to the attack in b) for the same reason as above. Any change in position in the blocks of the message will substantially change the ciphertext


### 8

??


### 9

74 in binary = 01001010

**1**001010 = $3$
1**0**01010 = $(3)^2$
10**0**1010 = $((3)^2)^2$
100**1**010 = $(((3)^2)^2)^2*3$
1001**0**10 =$((((3)^2)^2)^2*3)^2$
10010**1**0 = $(((((3)^2)^2)^2*3)^2)^2*3$
100101**0** = $((((((3)^2)^2)^2*3)^2)^2*3)^2$


### 10
e=3
N=999999999997
m=10000

**a)**

$c=m^{e} \text{ mod } N$
$10000^{3} \text{ mod } 999999999997=3$

**b)**

**c)**

**d)**

### 11
**a)**
We just need to find to sets of messages, $x,y$ that XOR together to the same value

$h'(00, 00)=h(00\oplus00) = h(00)$
$h'(11, 11)=h(11\oplus11) = h(00)$

**b)**

For any pair of messages $x,y$ we can find another pair $x',y'$ that xor together to the same value

If $x_{i} \oplus y_{i}=0$, they must both be $1$ or $0$. We set $(x'_{i}, y'_{i}) = (\neg x_{i}, \neg y_{i})$
If $x_{i} \oplus y_{i}=1$, one must be $1$ and the other $0$. We set $(x'_{i}, y'_{i})= (y_{i}, x_{i} )$ 

We have then ensured that no bit in $x,y$ is the same as in $x',y'$ yet still preserved $h'(x,y)=h'(x',y')$
 

### 12
a)
$m = 10^3 \text{ mod } 35$
$m = 1000 \text{ mod } 35$
$m = 20$

b)
We just need to find a number $\sigma^3=8$ since $N$ is so large
$\sigma=2$ 



### 13
$p=17$
$g=3\in \mathbb{Z}_{17}^{*}$
$a=3$
$b=5$

1. Alice choose random $a \in \mathbb{Z}_q$, ($a=3$)
2. Alice compute $A=g^{a}\text{ mod }p$, send to Bob ($3^{3} \text{ mod } 17 = 10$)
3. Bob choose random $b \in \mathbb{Z}_q$, ($b=5$)
4. Bob compute $B=g^{b}\text{ mod }p$, send to Alice ($3^{5} \text{ mod } 17 = 5$)
5. Alice output $k=B^{a} \text{ mod }p$ ($k=5^{3} \text{ mod } 17 = 6$ )
6. Bob output $k=A^{b} \text{ mod }p$  ($k=10^{3} \text{ mod }17=6$)
7. They now have the same $k$


### 14

