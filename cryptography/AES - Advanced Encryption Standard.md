# AES - Advanced Encryption Standard

- Blocks: 128 bits
- Keys: 
	- 128-bit - 10 rounds
	- 192-bit - 12 rounds
	- 256-bit - 14 rounds

## AES round transformation
Arrange the 16 input bytes in a $4\times4$ matrix

### Subfunctions
>[!tldr]- AddRoundKey (bit-wise XOR)
> $$b_{i,j}=a_{i,j}\,\oplus k_{i,j}$$
> 
> ![[AddRoundKey.png]]

>[!tldr]- SubBytes
> $$b_{i,j}=S(a_{i,j})$$
> - $S: \{0,1\}^{8}\rightarrow \{0,1\}^{8}$ is the invertible S-box
> - $S$ is a very simple non-linear function (field inversion)
> 
> ![[SubBytes.png]]

>[!tldr]- ShiftRows
> Rows shifted over different offsets: 0,1,2, and 3
> 
> ![[ShiftRows.png]]

>[!tldr]- MixColumns
> Bytes in columns are combined linearly
> $$b_{0,2}= \{2\}\times a_{0,2}+ \{3\}\times a_{1,2}+\{1\}\times a_{2,2}+\{1\}\times a_{3,2}$$
> Multiplication is a special field-multiplication
> 
> ![[MixColumns.png]]

![[Byte mixing in AES.png | 500]]

## AES - 10-round version

Arrange the 16 input bytes in a $4\times4$ matrix
- AddRoundKey
- "Do nine times"
	- SubBytes
	- ShiftRows
	- MixColumns
	- AddRoundKey
- SubBytes
- ShiftRows
- AddRoundKey

