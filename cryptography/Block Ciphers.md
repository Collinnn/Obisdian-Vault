# Block Ciphers

>[!info] Definition
> Block ciphers are one of the most **essential** parts of encryption.
> Example of usages:  [[Netværkssikkerhed#Transport Layer Security | TLS]]

- Much like [[Encryption Scheme]], except the key-space is $K$ instead of $\mathbb{K}$
- An example of a block-cipher is the [[Encryption Scheme#Examples |  Vigenére cipher]]
- We use block ciphers to construct [[Private-key encryption]]


How do we choose a good key for [[Security]]?
- **AES**: $n=128$

## Permutation
>[!info] Definition
> $$e_{k}: \{1,0\}^n \longrightarrow \{0,1\}^{n}$$
> such that $e_{k}(m) \neq e_{k}(m^{\prime})$ for all $m\neq m^{\prime}$

>[!tip] Notation
> Set of all permutations $\{0,1\}$ is denoted $S_{2^{n}}$


## PRP security game
"pseudorandom permutation"

TODO

### Examples
![[Vigenére#Vigenére for ASCII characters]]

## Modern Block Ciphers (SPN)
Substitution-permutation network

TODO

## Modes of operation for block ciphers

>[!example]- Slides
> ![[01410-symmetric-encryption-11-16.pdf]]




