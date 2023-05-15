# Post-quantum cryptography

[[Public-key Encryption]] and [[Diffie Hellman | Key-exchange]] can also be constructed using the hardness of:
- Lattice problems
- Solving systems of multivariate polynomial equations
- Decoding "obfuscated" error correction codes
- Finding an isogeny between supersingular elliptic curves


## Public key encryption and key exchange
- Lattice-based 
- Multivariate-polynomial-based 
- Code-based 
- Isogeny-based 

## Digital signatures
- Hash-based signatures
- MPC-in-the-head signatures


## NIST crypto standardization
- **Goal**: Standardize at least one PQ-sequre scheme of each:
	- Key Encapsulation Mechanism (KEM, ~public-key encryption)
	- Digital signature scheme (DSS)
- **Initially**: All classes represented
- To be standardized:
	- 1 Lattice KEM: Crystals-Kyber
	- 3 DSS: 
		- 2 based on lattices: Crystals-Dilithium&Falcon
		- 1 hash-based: SPHICS+
- 4th round: New call for signature proposals, 3 code-based KEMs under consideration

