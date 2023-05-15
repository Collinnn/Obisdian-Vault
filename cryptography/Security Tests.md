# Security Tests

## IND-CPA ([[Public-key Encryption]])
>[!tldr]- IND-CPA
> ![[Pasted image 20230514173105.png | 500]]
> 
> IND-CPA is a security property for encryption schemes that prevents attackers from distinguishing between ciphertexts produced by the scheme. This ensures that attackers cannot obtain information about the plaintext by analyzing the ciphertexts. It is an important property for encryption schemes used to protect sensitive information.
> 
> ### Problems
> - Deterministic
> 	- $m_{n}$ will always become $c_{n}$
> 
> ### Fails
> [[Public-key Encryption#RSA Cryptosystem| RSA]] fails, use [[RSA-OAEP]] 




## IND-CCA ([[Public-key Encryption]])
>[!tldr]- IND-CCA
> ![[Pasted image 20230514173144.png | 500]]
> 
> IND-CCA is a stronger security notion than IND-CPA for encryption schemes. It ensures that the encryption scheme is secure against attacks where an attacker can modify or create ciphertexts and observe their decryption. This property is important for encryption schemes used in applications where encrypted messages may be stored or transmitted over an insecure channel.
> 
> ### Problems
> - Malleable ciphertexts
> 	- We can change ciphertexts such that their plaintexts change in a predictable way
> 
> ### Fails
> [[Public-key Encryption#RSA Cryptosystem| RSA]] fails, use [[RSA-OAEP]]



## EUF-CMA ([[Digital Signatures]])
>[!tldr]- EUF-CMA
> ![[Pasted image 20230514173554.png | 500]]
> 
> EUF-CMA is a security property for digital signature schemes that prevents attackers from forging signatures on messages they have not seen before, even if they have access to a signing oracle. This is important for ensuring the authenticity and integrity of messages in applications such as electronic transactions and secure communications.


## DLOG- Discrete Logarithms ([[Discrete Logarithms]])
>[!tldr]- DLOG
> ![[Pasted image 20230514174258.png]]



## CDH - Computational [[ Diffie Hellman]] Problem
>[!tldr]- CDH
> Fix large primes $p,q$ where $q|p-1$
> Fix $g \in \mathbb{Z}_{p}^{*}$ such that $g$ has [[Order of a group element | order]] $q$
> 
> ![[Pasted image 20230514174059.png | 500]]
> 
> ### CDH vs DLOG
> - Attack on [[Discrete Logarithms | DLOG]] => Attack on CDH
> 	- If i can break [[Discrete Logarithms | DLOG]], then i can use that solution so break CDH
> 	- **not** the other way around
> 
> ![[CDH vs DLOG.png | 700]]


## DDH - Decisional [[Diffie Hellman]] Problem
>[!tldr]- DDH
> Similar to IND-CPA
> 
> Fix large primes $p,q$ where $q|p-1$
> Fix $g \in \mathbb{Z}_{p}^{*}$ such that $g$ has [[Order of a group element | order]] $q$
> 
> ![[Pasted image 20230514174133.png | 500]]
> 
> ### DDH vs CDH
> - Attack on CDH => Attack on DDH
> 	- If i can break CDH, then i can use that solution so break DDH
> 	- **not** the other way around (reverse is not known in general)
> 
> ![[Pasted image 20230514174159.png | 700]]


