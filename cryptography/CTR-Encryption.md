
The encryption can be defined as
$c_i=m_i \oplus e_k \oplus (iv \oplus i')$
where $i'$ is the n-bit string that represents i mod $2^n$ in binary, and $iv$ is an uniformly random
n-bit string.
Theorem 13.15. Encryption via the MAC-then-Encrypt method may not be IND-CPA secure when
instantiated with an IND-CPA encryption scheme and EUF-CMA secure MAC.
The decryption can be defined as 
$m_i=c_i \oplus e_k \oplus (iv \oplus i')$ NOTE: This is based on a description found online

>[!info] Theorem 13.15.
Encryption via the MAC-then-Encrypt method may not be IND-CPA secure when
instantiated with an IND-CPA encryption scheme and EUF-CMA secure MAC.

