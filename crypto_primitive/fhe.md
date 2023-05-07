# Fully Homomorphic Encryption

Fully homomorphic encryption (FHE) refers to the ability to calculate ciphertext without the private key. That is to say, for any valid f and plaintext m, there is a special property f(Enc(m)) = Enc(f(m)).

![image](../miscellaneous/img/fhe.png)

FHE is known as the holy grail of cryptography. This problem was proposed by Rivest in 1978. Thirty-odd years later, in 2009, Craig Gentry constructed the first FHE scheme.

At present, secure and efficient FHE schemes are based on the LWE problem and Ring-LWE problem on lattice. They are anti-quantum and can provide sufficient security even in the post-quantum era. 

Fully Homomorphic Encryption is restricted by efficiency, which mainly depends on the operation mode of ciphertext. While FHEW and TFHE cryptosystems are more suitable for dealing with boolean logic operations, BGV, BFV and CKKS are more suitable for batching and calculating affine transformations. For nonlinear arbitrary functions, the latest PBS technology has a good efficiency performance. Therefore, NuLink will build different FHE algorithms to improve efficiency. 

Fully Homomorphic Encryption has a wide range of theoretical and practical applications, especially in decentralized privacy-preserving products. 

Nodes in the system whose computing power is not strong enough can store their data in the Storage Layer in the form of ciphertext. When data computing is needed, the user initiates computing authorization to the computation nodes. The computation nodes carry on the corresponding ciphertext operation to get the encrypted result, the user downloads the result and decrypts it, and then the final plaintext result can be obtained. In the whole process of computing, only the owner of the data has the ability to decrypt, so users can be guaranteed data privacy. 

We need to emphasize that this can be used as a component of multi-party secure computing, rather than just completing the proxy computation of two parties.
