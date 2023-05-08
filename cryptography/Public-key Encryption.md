# Public-key Encryption

>[!tip] Tip
> When using RSA, use [[RSA-OAEP]] to make it IND-CCA secure (16.2.1 in the book)




A type of asymmetric-key Encryption

Involves two seperate but mathematically related keys per user
- One **private** one **public**
- Given public key, it is har to compute private key

**Confidentiality**
- The sender encrypts the message with the **public key** of the receiver
- Only receiver can decrypt it using private key

## Security

The adversary only wins the **IND-CPA** game with negligible probability.


## Coprimality

>[!faq] Solving coprimality question
> **Solve $a \cdot x = 1 \text{ mod } N$ by finding $x$**
> 
> 1. Rewrite equation: $a \cdot x + k \cdot N = 1$
> 2. If $gcd(a, N)= 1$ then $egcd(a,N)$ can compute $x$


## RSA Cryptosystem

**Key Generation:**
1. Find two large primes $p, q$ and $e$ with $gcd(e, (p-1)\cdot(q-1))=1$
2. Compute $N=p \cdot q$
3. Find $d$ such that $d \cdot e = 1 \text{ mod } (p-1)(q-1)$

Encrypt:
$m^{e}=c \text{ mod } N$

Decrypt:
$c^{d}=m \text{ mod } N$

>[!faq] Why is it secure?
> It is very hard to calculate the prime factorisation when you only have $e$


## PKE - IND-CPA
indistinguishability under chosen plaintext attack
![[IND-CPA.png]]

## PKE - IND-CCA
![[IND-CCA.png]]