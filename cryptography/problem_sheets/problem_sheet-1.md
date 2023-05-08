# problem_sheet-1

[[problem-sheet-1.pdf]]



$$
\begin{align}
α(x) · α(y) mod N^2 &= [(1 + xN) mod N^2] · [(1 + yN) mod N^2] mod N^2\\
&= (1 + xN + yN + xyN^2) mod N^2\\
&= (1 + (x + y)N + xyN^2) mod N^2\\
&= [(1 + (x + y)N) mod N^2] · [(1 + xyN) mod N^2] mod N^2\\
&= α(x + y mod N) · α(xy mod N)
\end{align}
$$



First we verify that $\alpha(x)$ and $\alpha(y)$ are in the group $\mathbb{Z}^{*}_{N^{2}}$. Because $\mathbb{Z}^{*}_{N^{2}}$ is the set of numbers that are coprime to $N^2$, we can check if $\alpha(x)$ and $\alpha(y)$ are in this set by showing that $\text{gcd}(\alpha(x),N^2)=1$ and $\text{gcd}(\alpha(y),N^2)=1$. 

$$
\begin{align}
\alpha(x)\cdot \alpha(y) \text{ mod } N^{2} &=\alpha(x+y\text{ mod } N) \\
\end{align}
$$

We expand using the $\alpha$ function

$$
\begin{align}
((1+xN) \text{ mod } N^2) \cdot ((1+yN) \text{ mod } N^2) \text{ mod } N^{2} 
&=
(1+(x+y\text{ mod } N) N) \text{ mod } N^2
\\
\end{align}
$$


|  x  |  y  | $\alpha(x)\cdot \alpha(y) \text{ mod } N^{2}$ | $\alpha(x+y\text{ mod } N)$ |
|:---:|:---:|:---------------------------------------------:|:---------------------------:|
| 10  | 22  |                     1057                      |            1057             | 
|  6  | 15  |                      694                      |             694             |
| 28  |  9  |                      133                      |             133             |


|  x  |  y  | $\alpha(x)^y \text{ mod } N^2$ | $\alpha(x\cdot y \text{ mod } N)$ |
|:---:|:---:|:------------------------------:|:---------------------------------:|
| 10  | 22  |              727               |                727                |
|  6  | 15  |              793               |                793                |
| 28  |  9  |              694               |                694                | 

---

---
|  x  |  y  | $\beta(x) \cdot \beta(y)$ | $\beta(x \cdot y ) \text{ mod } N^{2}$ |
|:---:|:---:|:-------------------------:|:--------------------------------------:|
|  2  |  3  |           11680           |                                        |
|  5  |  7  |           10500           |                                        |
| 11  |  9  |           1958            |                                        |



$$(x^{N}\text{ mod } N^2) \cdot (y^{N}\text{ mod } N^2)$$

$$ ((x \cdot y)^{N}\text{ mod } N^2) \text{ mod } N^{2}$$




$$\begin{aligned}
&β(x) = x^{N} \text{ mod } N^{2}= 7^{17} \text{ mod } 17^{2} &= 75\\
&β(y) = y^{N} \text{ mod } N^{2} = 9^{17} \text{ mod } 17^{2} &= 179\\
&β(x) \cdot β(y) = 75 \cdot 179 &= 13425\\
&β(x \cdot y) = (x \cdot y)^{N} \text{ mod } N^{2} = (7 \cdot9)^{17} \text{ mod } 17^{2}  &= 131\\
\end{aligned}
$$

And we notice that $13425 \text{ mod } 17^{2} = 131$. We therefore verified that the mapping is multiplicatively homomorphic $\text{mod } N^{2}$ 


---

Let N = 17, x = 7, y = 9 

---


We know that $H$ is collision-resistant and we assume that there exists a collision in $G^\prime$. 
Specifically there exists two inputs, $x=(x_{1}|x_{2}|x_{3}|x_4)$ and $x^\prime=(x^\prime_{1}|x^\prime_{2}|x^\prime_{3}|x^\prime_4)$ where $G^\prime(x) = G^\prime(x^\prime)$ and $x\neq x^\prime$

We would then have that: $H(H(x_{1}|x_{2})|H(x_{3}|x_{4})) =H(H(x^\prime_{1}|x^\prime_{2})|H(x^\prime_{3}|x^\prime_{4}))$

Since we know that $H$ is collision-resistant, it must be that $x_{1}|x_{2}=x^\prime_{1}|x^\prime_{2}$ and $x_3|x_{4} = x^\prime_3|x^\prime_4$, but this is not possible since $x$ and $x^\prime$ are distinct. Our assumption that there exists a collision in $G^\prime$ must be false then. 

--- 

# 9

To construct a collision-resistant hash function $G$ for inputs of length $n \cdot 2^k$ for arbitrary $k \in \mathbb{N}, k>1$,  we can recursively use $G^\prime$ from **Exercise 8.** 

As the length of the input is of length $n$, doubled $k$ times, we can recursively iterate on the input, applying the collision-resistant hash function $H$ as in **Exercise 8**. Since $H: \{0,1\}^{2n}\rightarrow \{0,1\}^n$ outputs with half that of the input length, we can recursively apply this function until the output has length $n$. 


Example: 


```
n: 4
input: 123456789ABCDEFG

1234       5678 9ABC       DEFG
|             | |             |
---H(x1|x2)---   ---H(x3|x4)---
       |                |
	  abcd             qrst
	   |                |
	   -----H(x1|x2)-----
				|
			   1Aaq
```


--- 


The Merkle-Damgård construction works by splitting the input message into blocks of a fixed size, and processing each block in turn using a compression function. The compression function takes the current state of the hash function and the current message block and produces the next state. As each iteration is reliant on the computed value of the one just before it, this process can not be parallelised. The runtime of the a program for Merkle-Damgård hashing will be linear with the input size, $O(n)$

The Merkle tree hashing algorithm can parallelise each "layer" of recursion (assuming that we can compute as many compressions in parallel as we need), since each computation is only reliant on the computations of the recursive call that it has called. In the example given in **Exercise 4**, we would initially call $H$ with the input string, which would recursively call two instances of $H$. These two could be computed in parallel, returned to the initial call and then that could be calculated. For a input of length 4 times that of the desired output, we would only create two "recursive layers" and thereby have to call the $H$ function in two batches. An example with the input of length 8 times that of the desired output would only result in three "recursive layers".  This results in a runtime of the Merkle tree hashing which would be logarithmic with regards to the input size, $O(\text{ln } n)$