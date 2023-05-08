# problem_sheet-2

## Exercise 2.1
1. It is not secure. As AND between two bits, only is 1 if both inputs also are 1. When the ciphertext is 1 at some position, it can therefore be concluded that both plaintext and key is 1. Information about the key and plaintext can be derived from the ciphertext. 

2. It is secure. As it is OTP encrypting on the same message, but twice, using two different keys, no information about the key or plaintext can be derived from either ciphertext independently. When in possession of both ciphertexts, the property of OTP where each plaintext are equally probable still holds. The two probabilities are independent and not correlated


## Exercise 2.2

```
Plaintexts
c   = grape
c´  = apple
c´´ = pears

Plaintexts as ascii in binary
c   = 1100111 1110010 1100001 1110000 1100101
c´  = 1100001 1110000 1110000 1101100 1100101
c´´ = 1110000 1100101 1100001 1110010 1110011

Ciphertexts in binary
c´´ = 0010111 0101100 1100111 1100011 1001101
c   = 0010001 0101110 1110110 1111111 1001101
c´  = 0000000 0111011 1100111 1100001 1011011

Key (broken using XOR from plain- and ciphertexts)
key = 1110000 1011110 0000110 0010011 0101000

Ciphertext c~ to decode in binary
c~  = 0000000 0101001 1101000 0110010 0001001

Plaintext of c~ decoded in binary
pt~ = 1110000 1110111 1101110 0100001 0100001

Plaintext of c~ decoded in ascii
pt~ = pwn!!


```