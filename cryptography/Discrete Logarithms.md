# Discrete Logarithms

## Discrete logarithms modulo a prime

Let $p$ be a prime

TODO: INSERT PICTURE SLIDE 12

**Regular logarithm** 
$2^{a}=1024$, solve for $a$, super easy

**Discrete logarithm**
$g^{a}=h \text{ mod }p$, solve for a, **REALLY HARD** 



>[!example] Example
> $p=17,g=3,h=14$
> 
> | a                     | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   |
> | --------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | $3^{a}\text{ mod }17$ | 3   | 9   | 10  | 13  | 5   | 15  | 11  | 16  | 14  |
> Answer is: $a=9$


### Hardness of DLOG
- When is DLOG difficult?
	1. $p$ is large prime (brute force attacks)
	2. $p-1$ must have at least one large prime factor
	3. $q$ must be large (brute force attacks)


[[Order of a group element]]
[[Lagrange's Theorem]]

