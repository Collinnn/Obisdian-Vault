# Hash Functions
Cryptographic Primitive

- $\text{H: } \{0,1\}^{*}\rightarrow \{0,1\}^{n}$

## Security properties:
>[!tip] Preimage resistance
> Given $h \in \{0,1\}^{n}$, it's **hard** to find $x\in \{0,1\}^{*}$ with $\text{H}(x)=h$
>
> *"Given a hash, it's hard to find a string that becomes that hash"*

>[!tip] Second-preimage resistance
> Given $x\in {0,1}^{*}$ it's hard to find $x^{\prime}\in \{0,1\}^{*}$, $x\neq x^\prime$ such that $\text{H}(x)=\text{H}(x^{\prime})$
>
> *"Given a string, it's hard to find another string such that they hash to the same hash"*
 
>[!tip] Collision resistance 
> It's hard to find $x$ and $x^\prime$, where $x\neq x^\prime$, such that $\text{H}(x)=\text{H}(x^{\prime})$
>
> *"It's hard to find collisions"*

## Construction
### Compression function
- $\text{C: }\{0,1\}^{2n} \rightarrow \{0,1\}^{n}$
- We can then use the same idea as block-wise encryption
- **Merkle-Damgård construction**:
	- $m\in \{0,1\}^{*}$, divide into $m=m_{1}||m_{2}||\dots||m_{e}$, $m_{i}\in\{0,1\}^n$
	- 



