# Probability
[[Statestik_noter.pdf]]


>[!info] Random variable (RV)
> Variable that takes on discrete values with certain probabilities


>[!info] Probability distribution (PD)
> A PD for a RV specifies the probabilities with which the variable takes on each possible value
> - Each probability must be between 0 and 1
> - The probabilities must sum to 1

>[!info] Event
> A particular occurrence in some experiments:
> - $\mathbf{PR[E]}$: probability of event $\mathbf{E}$

>[!info] Conditional probability
>  Probability that one event occurs, given that some other event occurred:
> - $\mathbf{Pr[A|B]} = \mathbf{Pr[A and B]}{Pr[B]} \equiv Pr[AB]/Pr[B]$ 

>[!info] Independence
> Two RV $\mathbf{X,Y}$ are **independant** if:
> - $\forall \,\mathbf{x,y:} \mathbf{Pr[X=x|Y=y]=Pr[X=x]}$

>[!info] Law of total probability
> Let $\mathbf{E}_{1}\dots \mathbf{E}_{n}$ are a partition of all possibilities. then $\forall \mathbf{A:}$
> $$\begin{align*}
> \mathbf{Pr[A]} &= \sum\limits_{i}\mathbf{Pr[AE_i]}\\
> & = \sum\limits_{i}\mathbf{Pr[A|E_i]\,\,Pr[E_{i}]}
> \end{align*}$$

