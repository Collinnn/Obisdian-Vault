# Quantum Computer



**Regular computer:**
- Specified by a bit $b \in \{0,1\}$
- Generally, bit strings: $x \in \{0,1\}^n$
- Basic operations: Logic gates

**Quantum information**
- "What is the polarization of the light emitted from the flashlight"
- Specified by a unit vector $|v\rangle \in \mathbb{R}^2$
- Generally: unit vectors $|\Psi\rangle \in \mathbb{C}^{2n}$ (bit strings: basis)
- Basic operations: "Quantum gates" <-> Unitary matches

## Vulnerable encryption schemes
- RSA
- Diffie-Hellman (ordinary and elliptic curve
- => All* currently used public-key cryptography


>[!tip]- TLS used by dtu.dk and vulnerabilities
> ![[TLS example.png]]


Factoring two numbers is normally computationally hard, but not with quantum computers

### Factoring

How does a quantum computer factor integers?

**Problem**: given $N$ not prime, find $q \notin \{1,N\}$ such that $q|N$
**Algorithm:**
1. Pick a random $a$ with $1<a<N$
2. Compute $gcd(a,N)$. if its $\neq 1$ we found a factor (Yay!)
3. Otherwise, let $f(x)=a^{x} \text{ mod } N$, find $r < N$ with $f(x+r) = f(x)$
4. Hope that $r$ is even and $-1 \neq a^{r/ 2} \text{ mod } N$
5. Output $gcd(a^{r/2}-1,N)$
   
In step 3, finding $r$ is called the **period-finding problem**, and is solved in **linear** time using Fourier transform sampling with 
traditional computers, and in **logarithmic** time using quantum computers.

