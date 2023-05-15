# Attack Types

1.  **Brute-force attacks:** This type of attack involves trying every possible key until the correct one is found. The effectiveness of this attack depends on the key size and the amount of computational power available to the attacker.
    
2.  **Known-plaintext attacks:** This type of attack involves an attacker having access to both the plaintext and the corresponding ciphertext for one or more blocks of data. With this information, the attacker can derive the key and decrypt the rest of the message.
    
3.  **Chosen-plaintext attacks:** This type of attack involves an attacker having the ability to choose the plaintext blocks that are encrypted with the cipher. This allows the attacker to gain information about the key and eventually decrypt the message.
    
4.  **Side-channel attacks:** These attacks exploit weaknesses in the implementation of the block cipher, such as power consumption or electromagnetic radiation, to derive information about the key.
    
5.  **Differential cryptanalysis:** This type of attack involves analyzing the differences between pairs of plaintexts and their corresponding ciphertexts to derive information about the key. This type of attack can be effective against block ciphers that have weaknesses in their round functions.
    
6.  **Linear cryptanalysis:** This type of attack involves finding a linear approximation of the block cipher that allows the attacker to derive information about the key. This attack can also be effective against block ciphers that have weaknesses in their round functions.
    
7.  **Meet-in-the-middle attack:** This type of attack involves encrypting a plaintext with every possible key and storing the results in a table. The attacker then encrypts the ciphertext using every possible key and looks for matches in the table. This type of attack can be effective against block ciphers with small block sizes and key lengths.
    
8.  **Weak keys:** Some block ciphers may have certain key values that produce weak or predictable ciphertexts. An attacker can exploit this weakness to derive the key and decrypt the message.
    
9.  **IV reuse**: Initialization vectors (IVs) are used to ensure the uniqueness of the ciphertext produced by a block cipher. If the same IV is used for multiple messages, an attacker can exploit this weakness to derive information about the key and decrypt the messages.
    
10.  **Malleability**: Block ciphers can be vulnerable to malleability attacks, where an attacker can modify the ciphertext in a predictable way to obtain a modified plaintext. This can be a problem if the message has integrity requirements and the attacker is able to modify the message without detection.


## Other list
-   Reuse of nonce: Using the same "nonce" (number used only once) to generate encryption keys in a symmetric key encryption scheme, which can result in encryption keys being reused and the system becoming vulnerable to attacks.
    
-   Time-memory trade-off attacks: A class of attacks that trade space (memory) for time by precomputing data, such as rainbow tables, to speed up attacks on cryptographic systems.
    
-   Brute-force attack on key: A type of attack where an attacker systematically tries all possible key combinations to decrypt an encrypted message.
    
-   Known plaintext attack (KPA): An attack where the attacker has knowledge of some plaintext and corresponding ciphertext and attempts to use this knowledge to determine the encryption key.
    
-   Chosen plaintext attack (CPA): An attack where the attacker can choose plaintext messages and obtain the corresponding ciphertext, and then use this information to try to deduce the encryption key.
    
-   Adaptive chosen plaintext attack (ACPA): An attack where the attacker can choose plaintext messages and obtain the corresponding ciphertext, but also has the ability to adaptively choose subsequent plaintext messages based on the previous ciphertexts received.
    
-   Chosen ciphertext attack (CCA): An attack where the attacker has the ability to choose ciphertext messages and obtain the corresponding plaintext, and then use this information to try to deduce the encryption key.
    
-   Padding oracle attack: An attack that exploits the behavior of an oracle (a system that can answer questions about the encrypted message) that provides information about whether the padding in a message is correct or not.
    
-   Bit flipping attack: An attack that exploits the fact that the attacker can modify the ciphertext to flip certain bits in the plaintext without knowledge of the encryption key.
    
-   Block swapping attack: An attack that rearranges the order of ciphertext blocks to manipulate the decrypted message, potentially causing the decryption to be completely different from the original message.
    
-   IV manipulation attack: An attack that exploits weaknesses in the initialization vector (IV) in a block cipher mode, which can allow the attacker to manipulate the ciphertext or even recover the encryption key.
    
-   Replay attack: An attack where an attacker intercepts a message and resends it later to achieve some malicious goal.
    
-   Ciphertext only attack (COA): An attack where the attacker has access only to the ciphertext and tries to deduce the encryption key or the plaintext.
    
-   Adaptive chosen ciphertext attack (ACCA): An attack where the attacker can adaptively choose ciphertext messages and obtain the corresponding plaintext, and can also modify ciphertext messages to try to deduce the encryption key.
    
-   Birthday attack: A type of attack that exploits the birthday paradox (the probability that two people in a room share a birthday when there are more than 23 people) to find collisions in hash functions or cryptographic systems.