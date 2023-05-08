# Greatest Common Divisor

>[!info] Definition
> The largest possible integer $d$ such that $d|x$ and $d|y$
> 
> >[!example]- Examples
> > - $gcd(12,8)=4$
> > - $gcd(9,3)=3$
> > - $gcd(11,12)=1$
> 

## Properties
>[!tip] Coprime
> If $gcd(x,y)=1$ then we say $x, y$ is coprime

## The Euclidean algorithm
An algorithm to compute the $gcd$

>[!info] Algorithm
> To compute $gcd(x,y)$
> 1. Define $r_{0}=x, r_{1}=y$
> 2. Iteratively in round $i \in \{1,\dots\}$
> 	1. Divide $r_{(i-1)}$ by $r_{i}$, obtaining remainder $r_{i+1}$ (i.e. $r_{i+1}=r_{i-1} \text{ mod } r_{i}$)
> 	2. If $r_{i+1}=0$ output $r_{i}$
> 	
> >[!example]- Example
> > $gcd(12,7)$
> > 
> > | 1.  | $5=12-7 \cdot 1$ |
> > | --- | ---------------- |
> > | 2.  | $2=7-5 \cdot 1$ |
> > | 3.  | $1=5-2 \cdot 2$ |
> > | 4.  | $0=2-1 \cdot 2$ | 

- Always terminates

### Extended
In addition to Euclidean Algorithm, keep track of linear combinations
- Write GCD as linear combination of the two inputs. 

>[!example] Example
> $gcd(12,7)$
> 
> | 1.  | $5=1 \cdot 12-7 \cdot 1$ |
> | --- | ---------------- |
> | 2.  | $2=7-5 \cdot 1 = 7 - (1\cdot12-7\cdot1 )\cdot1=-1\cdot12+7\cdot2$ |
> | 3.  | $1=5-2 \cdot 2=(1\cdot12-7\cdot1)-(-1\cdot12 + 7\cdot2 )\cdot2 = 3\cdot12 - 7\cdot5$ |
> | 4.  | $0=2-1 \cdot 2$ | 