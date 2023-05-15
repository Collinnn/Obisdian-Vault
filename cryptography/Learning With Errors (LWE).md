# Learning With Errors (LWE)


Following linear system over $\mathbb{Z}_{23}$ using Gaussian elimination:
$$
\begin{pmatrix}
1 & 2 \\ 3 & 4  \\ 5 & 6
\end{pmatrix}

\begin{pmatrix}
13 \\ 20
\end{pmatrix}
 = 
\begin{pmatrix}
7 \\ 4 \\ 1
\end{pmatrix}

\text{ mod }
23
$$

Hint: $21^{-1}=11 \text{ mod } 23$


## LWE


Following linear system over $\mathbb{Z}_{23}$ using Gaussian elimination:
$$
\begin{pmatrix}
1 & 2 \\ 3 & 4  \\ 5 & 6
\end{pmatrix}

\begin{pmatrix}
9 \\ 10
\end{pmatrix}
 = 
\begin{pmatrix}
6 \\ 19 \\ 13
\end{pmatrix}
+
\begin{pmatrix}
\varepsilon_1 \\ \varepsilon_{2} \\ \varepsilon_{3}
\end{pmatrix}

\text{ mod }
23
$$

where $\varepsilon_{i}\in \{-1,0,1\}$ for $i=1,2,3$

Hint: $21^{-1}=11 \text{ mod } 23$
