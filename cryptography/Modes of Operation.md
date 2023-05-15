# Modes of Operation

## EBC 
Dangerous, dont use
![[EBC mode.png| 500]]

### Vulnerabilities
-   Repeated plaintext vulnerability
-   Block permutation vulnerability
-   Deterministic encryption vulnerability
-   Bit-flipping vulnerability

## CBC
![[CBC mode.png| 500]]

### Vulnerabilities
-   Padding oracle vulnerability
-   Initialization vector (IV) misuse vulnerability
-   Chosen plaintext attack vulnerability
-   Data manipulation vulnerability
## CTR
![[CTR mode.png| 500]]


### Vulnerabilities
-   Nonce reuse vulnerability
-   Randomness reuse vulnerability
-   Encryption key reuse vulnerability
-   Bit flipping vulnerability
   
# Attacks
-   Repeated plaintext vulnerability: Occurs when the same plaintext message is encrypted multiple times using the same key, making it easier for an attacker to recover the plaintext by comparing ciphertexts.
-   Block permutation vulnerability: Occurs when the cipher operates on a block of plaintext as a fixed unit, allowing an attacker to re-arrange blocks of ciphertext to produce new valid ciphertexts.
-   Deterministic encryption vulnerability: Occurs when the same plaintext always produces the same ciphertext, allowing an attacker to observe patterns in the ciphertext and potentially recover the plaintext.
-   Bit-flipping vulnerability: Occurs when an attacker is able to change individual bits of ciphertext, leading to corresponding changes in the plaintext when decrypted.
-   Nonce reuse vulnerability: Occurs when the same "nonce" value is used to encrypt two different messages with the same key, allowing an attacker to derive information about the plaintext.
-   Randomness reuse vulnerability: Occurs when the same random value is used multiple times, allowing an attacker to observe patterns in the ciphertext and potentially recover the plaintext.
-   Encryption key reuse vulnerability: Occurs when the same encryption key is used to encrypt multiple messages, allowing an attacker to observe patterns in the ciphertext and potentially recover the key or plaintext.
-   Padding oracle vulnerability: Occurs when an attacker is able to interact with a decryption oracle that reveals whether the padding of a ciphertext message is correct or not, allowing the attacker to recover the plaintext.
-   Initialization vector (IV) misuse vulnerability: Occurs when the IV is not properly randomized, allowing an attacker to observe patterns in the ciphertext and potentially recover the key or plaintext.
-   Chosen plaintext attack vulnerability: Occurs when an attacker is able to choose and encrypt their own plaintext messages, allowing them to analyze the corresponding ciphertext and potentially recover the key or plaintext.
-   Data manipulation vulnerability: Occurs when an attacker is able to modify the plaintext of a message in transit without detection, potentially leading to unauthorized access or other attacks.