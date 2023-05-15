# Message Authentication Codes (MACs)

>[!info] Definition
> The purpose of a MAC is to verify that a message has not been tampered with during transmission and that it originates from a trusted source.
> 
> The way a MAC works is by using a **secret key** to generate a fixed-size code, which is attached to the message being sent. The recipient of the message can then use the **same key** to generate the code themselves and compare it with the one that was sent. If the two **codes match**, the recipient can be **sure** that the message has not been altered in transit and that it comes from the **expected sender**

>[!warning] IMPORTANT
> NEEDS TO BE INVERSIBLE



## Algorithms

>[!tip] MAC algorithm: $\text{Mac}$
> - **Input**: $(\text{key } k, \text{message } m)$
> - **Output**: $\text{tag }t$
> - **Denoted**: $t \leftarrow \text{Mac}_{k}(m)$

>[!tip] Verify algorithm: $\text{Verify}$
> - **Input**: $(\text{key } k, \text{message } m, \text{tag } t)$
> - **Output**: $\text{bool } valid$
> - **Denoted**: $b \leftarrow \text{Verify}_{k}(m,t)$
> 	- Computes whether or not the tag is valid for the key and message

### Example

>[!example] Example
> Fixed-length MAC using [[Security#Example: One-time Pad | One-time Pad]]
> - $m \in \{0,1\}^{128}$
> - $\text{Mac}_{k}(m)=m\oplus k$
> - $\text{Verify}(m,t)= \text{outpur valid if } m \oplus t = k$
> 
> ***NOT GOOD***:
> You can flip a bit in the message and the tag, and the verify algorithm will return that the tag is valid for the message. See [[Message Authentication Codes#Non-malleability | non-malleability]]

>[!example] Example 2
> Choosing the MAC to be [[Block Ciphers]] -> [[Block Ciphers#Modes of operation for block ciphers | CBC]]. 
> - This is vulnerable to "length-extension-attacks" if the messages are dynamic length
> - **Proven secure** if message length is fixed
> - **Can be fixed:**
> 	- By adding some "post-process" information at the end of the CBC-chain to "encode" the length into the tag.


## HMAC
HMAC (Hash-based Message Authentication Code) is a type of MAC algorithm that uses a cryptographic [[hash functions | Hash function]] in combination with a secret key to produce a fixed-size output. HMAC is used for symmetric authentication to verify the integrity and authenticity of a message between two parties that share a secret key.





## Deterministic MAC w. canonical verification
If the same **message** with the same **key** *always* produces the same **tag**, the MAC algorithm is deterministic. 

Canonical verification means that the MAC is verified in a specific, standardized way.
The canonical verification process typically involves computing the MAC of the received message using the same key and comparing it to the recieved tag.



## MAC security

### Non-malleability
An encryption algorithm is "malleable" if it is possible to transform a **ciphertext** into another **ciphertext** which decrypts to a related **plaintext**

### EUF-CMA game
**Existential Unforgeability under Adaptive Chosen Message Attack**

-   The attacker $\mathcal{A}$'s goal is to forge a valid signature on a message they have not seen before.
-   The defender's goal is to prevent the attacker from forging a valid signature on a new message.
-   The attacker can choose any number of messages to sign and observe the corresponding signatures.
-   The attacker can adapt their strategy based on the information they receive.
-   The EUF-CMA game is an adaptive chosen message attack because the attacker is allowed to choose the messages they want to sign and observe the corresponding signatures repeatedly.
-   The attacker wins the game if they successfully **forge** a valid signature on a new message.


