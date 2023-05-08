# Security

What does it mean for a [[Encryption Scheme]] to be secure?
- What do we want the adversary to not be able to achieve?
- What are the capabilities of the adversary?

Formal definitions enable meaningful analysis, evaluation and comparison of schemes

## Secure encryption definition

>[!info] Perfect secrecy
> Regardless of any **prior information** the adversary has about the plaintext, the ciphertext should leak **no additional information** about the plaintext


- $\mathcal{A}$ **does not learn the plaintext from the ciphertext**
	- What if the adversary learns only a part of the plaintext
	- What if the adversary is able to learn som partial information about the plaintext? (e.g. salary > 30.000 DKK)
- $\mathcal{A}$ **does not learn the key**
	- Consider the scheme $e_{k}(m)=m$



## Adversary attacks
- Ciphertext-only attack ($\mathcal{A}$ has access only at ciphertext, specifically):
	- One ciphertext
	- Many cipher-texts
- Known-plaintext attack ($\mathcal{A}$ has access to pairs of known plaintexts and their corresponding ciphertexts)
- Chosen-plaintext attack ($\mathcal{A}$ has the ability to choose plaintexts and to view their corresponding ciphertexts)
- Chosen-ciphertext attack ($\mathcal{A}$ has the ability to obtain the decryption of ciphertexts of its choice)


## Probability Distributions


>[!info] The random variable $\mathbf{M}$
> - $\mathbf{M}$ is the random variable denoting the value of the message
> - $\mathbf{M}$ ranges over $\mathbb{M}$
> - Reflects the likelihood of different messages being sent, given the adversary's prior knowledge

>[!info] The random variable $\mathbf{K}$
> - $\mathbf{K}$ is the random variable denoting the key
> - $\mathbf{K}$ ranges over $\mathbb{K}$
> - $KeyGen$ defines a [[cryptography/Probability | probability distribution]] for the random variable $\mathbf{K}$
> - $\mathbf{Pr[K=k]=Pr[}KeyGen \text{ outputs key } \mathbf{k]}$

>[!info] The random variable $\mathbf{C}$
> - For some encryption scheme $(KeyGen, e, d)$ and some [[cryptography/Probability | probability distribution]] for $\mathbf{M}$
> 	- Generate a key $k$ using $KeyGen$
> 	- Choose a message $m$, according to the given PD
> 	- Compute $c\leftarrow e_{k}(m)$
> - Then $\mathbf{C}$ is the random variable denoting the value of the ciphertext in this experiment

### Example: One-time Pad
For a message of length $p$ get key of length $p$ using $KeyGen$ from a uniform distribution, and encrypt by modular addition. 
As decrypting a ciphertext with every key returns every possible plaintext, OTP resists even brute force attack, and therefore fulfills perfect secrecy

>[!note]- Slides
> ![[2_secure-encryption-23-38.pdf]]

