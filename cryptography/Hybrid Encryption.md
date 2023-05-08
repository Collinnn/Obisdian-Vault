# Hybrid Encryption

>[!info] Definition
> Combining the efficiency of [[Encryption Scheme#Symmetric-key encryption scheme | symmetric encryption]] with the convenience of [[Public-key Encryption | public-key (asymmetric) encryption]]




AES vs. RSA on a modern AMD Ryzen 9 5950X from 2020. 16 cores but we only use 1.

- AES-128 
	1. It takes around 16 cycles per byte (https://bench.cr.yp.to/results-stream.html) to encrypt/decrypt AES-128. For a whole ciphertext of 16 bytes, that is around 256 cycles. 
	2. The processor runs at 3.400 MHz, i.e. it performs 3.400.000.000 cycles per second. 
	3. One core can approximately encrypt/decrypt 13.300.000 ciphertexts per second. 
- RSA w/ 2048 bit keys 
	1. Encryption with small exponent: ≈ 12.000 cycles 
	2. Decryption: ≈ 2.400.000 cycles (from https://bench.cr.yp.to/results-kem.html )

## Key encapsulation
- PKE scheme $Enc^{Pub}, Dec^{Pub}$
- SKE echeme $Enc^{Sym}, Dec^{Sym}$

![[key_encapsulation.png]]