### Decision LWE

>[!info] Definition (Mostly transcriped from Blackboard)
> $y=y_0=A x+\epsilon$
> where $y,x,\epsilon$ are vectors and $A$ is an matrix
> $c_i = r^T\times y +m[\frac q 2 ]$ where $Z_q$, independant of m.
> $b'=m\oplus m'$ uniformly random bit
> 
> 
> Let $A,x,y,\epsilon$ be as above, and set $y_0=y$, where $y_i \leftarrow Z_q^n$ 
> Sample $b \leftarrow (0,1)$ 
> Given $A,y_b$ , find b.
>$(A)\times(x)=(y) + \epsilon$
> 
> >[!example]- Example without $\epsilon$
> > Find $x,y$ for the following matrix, 
> > Note If with epsilon bruteforce is normally the best option.
> > $<1,2;3,4;5,6>\times <x,y> = <5,20,12>$
> > ![[Pasted image 20230512202724.png]]
>> 



![[Pasted image 20230512201224.png]]

### The search LWE problem
Let $q$ be a prime. Let $A\in Z_q^{n\times m}$ piched at $x\in Z_q^{m}$ random and $\epsilon$ ~$p_0^m$ $(\epsilon \in Z^m, y=A\times x + \epsilon)$
Given $(A,y)$, find $x$.




### Efficiency Improvement
Reuse A for many x's & y's
Use the advantages of modulo by being memory effiecent in only being in a part of it
Replace matrix mult with polynomial mult (also efficent to stop qbit problems)
Matrixes of polynominals
Simplify the error distribution

### Discrete Gaussian distribution

Continnous: mean $\mu$ , variance $\sigma^2$ density
$d(x)_{r,\sigma} = \frac 1 {\sqrt {2 \Pi \sigma^2}}\times e^{\frac {-(x-\mu)^2} {2\sigma^2}}$    
Discrete: mean 0 
1. attempt $p(n)=N_6 e^{\frac {-n^2} {2\sigma^2}}$
2. attempt $y = x$ ($x \in [n-\frac 1 2 , n+\frac 1 2] \rightarrow y=n$)
