# Square and multiply


![[Pasted image 20230513203441.png]]


The square-and-multiply algorithm is an efficient method for computing exponentiations modulo m, especially when the exponent is large. It works by representing the exponent as a binary number and then computing the powers of $x$ iteratively by squaring the previous result and multiplying it by $x$ if the corresponding bit in the binary representation of the exponent is $1$.

To compute $x^{219}$ mod m using the square-and-multiply method, we first convert the exponent $219$ to binary: $219 = 11011011_2$. Then, we apply the algorithm as follows:

1.  Start with $r = x \text{ mod } m$
2.  For each bit in the binary representation of the exponent (from left to right): 
	a. Square $r$ modulo $m$. 
	b. If the bit is $1$, multiply $r$ by $x$ modulo $m$.
3.  Return $r$.

Using this algorithm, we need $8$ modular squarings and $6$ modular multiplications to compute $x^219 \text{ mod } m$.

To compute $x^{319}$ mod m using the same method, we first convert the exponent $319$ to binary: $319 = 100111111_2$. Then, we apply the algorithm.
Using this algorithm, we need $8$ modular squarings and $7$ modular multiplications to compute $x^{319} \text{ mod } m$.


## Alternate
![[Pasted image 20230514115848.png]]




**Example**
74 in binary = 01001010

**1**001010 = $3$
1**0**01010 = $(3)^2$
10**0**1010 = $((3)^2)^2$
100**1**010 = $(((3)^2)^2)^2*3$
1001**0**10 =$((((3)^2)^2)^2*3)^2$
10010**1**0 = $(((((3)^2)^2)^2*3)^2)^2*3$
100101**0** = $((((((3)^2)^2)^2*3)^2)^2*3)^2$