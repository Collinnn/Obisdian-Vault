# RSA-OAEP

Type of [[Public-key Encryption]]

- $k= 8 \cdot\lfloor log_{8} N \rfloor$ and $k_{0}, k_{1} > 128, n=k-k_{0}-k_{1}$
- Messages $m \in \{0,1\}^{n}$
- Hash functions: 
	- $G:\{0,1\}^{k_{0}} \rightarrow \{0,1\}^{n+k_{1}}$
	- $H:\{0,1\}^{n+k_{1}} \rightarrow \{0,1\}^{k_{0}}$
## Encryption
Encryption for $m,N,e$
1. Sample random bit string $R \in \{0,1\}^k_{0}$
2. Compute $A=[(m|0^{k_{1}}) \oplus G(R), R\oplus H((m|0^{k_{1}})\oplus G(R))]$
3. Set $c=A^{e} \text{ mod } N$

## Decryption
1. Compute $A^{\prime} = c^{d} \text{ mod } N$ and check if $A^{\prime} < 2^{k}$
2. Let $A^{\prime}=[B_{0},B_{1}]$ and compute $R^{\prime}=H(B_{0})\oplus B_{1}$
3. Compute $m^{\prime}=B_{0}\oplus G(R^{\prime})$
   If $m^{\prime}$ ends with $k_{1}$ 0's then recover $m$

## Why it works
- Ind [[Public-key Encryption#PKE - IND-CPA | IND-CPA]] every choice of $R, m$ gives different $A$, ($2^{k_{0}}$  many) 
- Because of the XOR in "$(m|0^{k_{1}})\oplus G(R))$", changing 1 bit in $m$ or $R$ creates an entirely different block
	- Therefore, related messages don't have an algebraic relation

