# Modular arithmetic

- $N$: **Modulus**, positive integer
- $a$:
- $b$: **Remainder**
	- $Z_{n}=\{0,\dots, N-1\}$

If we divide $a$ by $N$ over the integers, then $a=b+kN$ where $0\leq b < N$ is unique

We call $b$ the remainder of the division.

>[!tip] Congruency
> Two integers $a, b$ are called congruent if $N|(b-a)$ and we write $a=b \text{ (mod } N)$
> >[!example] Example
> $24 = 2 \text{ mod } 11$
> $24+3 = (2+3) \text{ mod } 11$
> $24\cdot3 = (2\cdot3) \text{ mod } 11$

>[!tip] Property
> Since: 
> - $0=N(\text{mod }N)$, 
> - $1=N+1(\text{mod }N)$,
> - $...$
> 
> Every integer is equal to $0,\dots, N-1 \text{ modulo } N$


## Rules of modular arithmetic

>[!info] Rule 1
> If $a=x \text{ mod } N$ and $b=y \text{ mod } N$ then
> 1. $a+b=x+y \text{ mod }N$
> 2. $a \cdot b = x \cdot y \text{ mod }N$

>[!info] Rule 2: Associativity
> $(a+b)+c=a+(b+c) \text{ mod } N$ and $(a \cdot b) \cdot c = a \cdot (b \cdot c)$

>[!info] Rule 3: Commutativity
> $a+b=b+a \text{ mod }N$ and $a \cdot b=b \cdot a \text{ mod }N$

>[!info] Rule 4: Identity elements
> $a+0=a \text{ mod } N$ and $a+1 = a \text{ mod } N+1$

>[!info] Rule 5: Distributivity
> $(a+b)\cdot c=a \cdot c + b \cdot c \text{ mod } N$

>[!info] Rule 6
> $a+(N-a)=0 \text{ mod }N$


