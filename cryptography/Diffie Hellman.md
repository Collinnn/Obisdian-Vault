# Diffie Hellman
## Key agreement
- Alice and Bob agrees on:
	- Large primes $p,q$ where $q|p-1$
	- Fix $g \in \mathbb{Z}_{p}^{*}$ such that $g$ has [[Order of a group element | order]] $q$
	- Works for any finite group $G$ of prime order $q$ instead of $\mathbb{Z}_{p}^{*}$


1. Alice choose random $a \in \mathbb{Z}_q$
2. Alice compute $A=g^{a}\text{ mod }p$, send to Bob
3. Bob choose random $b \in \mathbb{Z}_q$
4. Bob compute $B=g^{b}\text{ mod }p$, send to Alice
5. Alice output $k=B^{a} \text{ mod }p$
6. Bob output $k=A^{a} \text{ mod }p$ 
7. They now have the same $k$


Works because
$$B^{a}=(g^{b})^{a}=g^{ab}=(g^{a})^{b}=A^{b}$$

## Drawbacks of Diffie Hellman
- No security against Man-in-the-middle attack


## In practice
Elliptic-curve groups are used instead.


## Security

Adversary task:
- Given $g,A,B$ find $k$
- Clearly [[Discrete Logarithms | DLOG]] is hard
	- But breaking DH is not the same as DLOG

### CDH - Computational Diffie Hellman Problem
Fix large primes $p,q$ where $q|p-1$
Fix $g \in \mathbb{Z}_{p}^{*}$ such that $g$ has [[Order of a group element | order]] $q$


- Challenger:
	- Choose $a,b \in Z_{q}$

- Attacker:
	- **recieves**: $g, g^{a},g^{b}$
	- **returns**: $h$
		- Wins if $h=h^{a*b}$

#### CDH vs DLOG
- Attack on [[Discrete Logarithms | DLOG]] => Attack on CDH
	- If i can break [[Discrete Logarithms | DLOG]], then i can use that solution so break CDH
	- **not** the other way around

![[CDH vs DLOG.png]]


### DDH - Decisional Diffie Hellman Problem
Similar to [[Public-key Encryption#PKE - IND-CPA]]

Fix large primes $p,q$ where $q|p-1$
Fix $g \in \mathbb{Z}_{p}^{*}$ such that $g$ has [[Order of a group element | order]] $q$


- Challenger:
	- Choose $a,b,r \in Z_{q}$
	- Choose random bit $d$
	- $c=\begin{cases}r & \text{if }d=0\\a \cdot b & \text{ if }d=1\end{cases}$

- Attacker:
	- **recieves**: $g, g^{a},g^{b},g^{c}$
	- **returns**: $\hat{d}$
		- Wins if $\hat{d}=d$

#### DDH vs CDH
- Attack on CDH => Attack on DDH
	- If i can break CDH, then i can use that solution so break DDH
	- **not** the other way around (reverse is not known in general)
