# Encryption Scheme

>[!info] Definition
> Set of algorithms for encrypting and decrypting 

Always implemented using [[Kerkhoffs' principle]]

## Symmetric-key encryption scheme
"Symmetric-key" - same key used for encrypting and decrypting

- $\mathbb{K}$ **(key space)**: Set of all possible keys
- $\mathbb{M}$ **(message space)**: Set of all possible messages
- $\mathbb{C}$ **(cipher-text space)**: Set of all possible cipher-texts


>[!tip] Encryption algorithm: $e$
> - **Input**: $(\text{key } k, \text{message } m)$
> - **Output**: $\text{ciphertext }c$
> - **Denoted**: $c \leftarrow e_{k}(m)$, where $k \text{ in } \mathbb{K}, m \text{ in } \mathbb{M}, c \text{ in } \mathbb{C}$
> 	- Not well defined ($\leftarrow$) as modern algorithms are random. 

>[!tip] Decryption algorithm: $d$
> - **Input**:  $(\text{key } k, \text{cyphertext } c)$
> - **Output**: $\text{message } m$
> - **Denoted**: $d_k(c)=m$ 
> 	- Well defined ($=$) because function is deterministic ([not injective](https://en.m.wikipedia.org/wiki/Injective_function))

>[!tip] Key generation algorithm: $KeyGen()$
> - **Input**: 
> - **Output**: $\text{key} k$
> - **Denoted**: $k \leftarrow KeyGen()$




### Properties 
- **Correctness**:  $m^{\prime}=m$
	- $c \leftarrow e_{k}(m)$
	- $d_k(c)=m^\prime$


## Examples
>[!example] Examples
> ### Caesar's Cipher
> - $\mathbb{K}=\{0,1,..,25\}$ (every letter)
> - $\mathbb{M}=\{A,...,Z, \textvisiblespace\}^k$
> - $\mathbb{C} =\mathbb{M}$
> - $A=c_{0}, B=c_{1}, ..., Z=c_{25}$
> 
> For a character $a \text{ in } \mathbb{A}$:
> $$e_{k}(a) = 
> \begin{cases}
>  \textvisiblespace & a=\textvisiblespace \\ \\
>  c_{(i+k \text{ mod } 26)} & a=c_i
> \end{cases}
> $$
> 
> ### Vigenére cipher
> ![[Vigenére#Vigenére]]

## Disadvantages

The **chicken-and-egg** problem
- You need a shared key $k$ to establish a secure channel
- You need a secure channel to share the key

**Scalability problems**