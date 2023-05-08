# Vigenére
Have a set of keys, and use Caesar cipher where each letter uses the next key.

## Problems with Vigenére
- Every output byte depends on 1 input byte
- I's linear: $e_{k}(m)+e_{k}(m^{\prime}) \text{ mod } 128 = e_{k}(m+m^{\prime} \text{ mod }128)$

## Vigenére for ASCII characters

>[!info] Definition
> - $n=128(=16 \text{ bytes})$
> - $k=k_{1}k_{2}\dots k_{16}, \quad k_{i}\in \{0,\dots,127\}$
> - $m=m_{1}m_{2}\dots m_{16}, \quad m_{i} \in \{0,\dots,127\}$
> - $e_{k}(m)=c_{1},\dots,c_{16}, \quad c_{i}=k_{i}+m_{i} \text{ mod } 128$ 



Easy to win in the [[Block Ciphers#PRP security game | PRP security game]]
1. Send message $m_{1}$, receive ciphertext $c_{1}$
2. $c_{1}-m_{1} \text{ mod }128=k_{1}$ (using bytewise subtraction)
3. Repeat with new message $m_{2}$
4. If $k_{1}=k_{2}$ then we are sure its not uniformly random   