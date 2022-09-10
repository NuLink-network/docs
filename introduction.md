# Introduction


NuLink network is a decentralized solution for privacy-preserving applications developers to implement best practices and best of breed security and privacy. The NuLink network  provides endpoint encryption and cryptographic access control. Sensitive user data can be securely shared from any user platform to cloud or decentralized storage and access to that data is granted automatically by policy in Proxy Re-Encryption or Attribute-Based Encryption. For the data user on the other side, Zero-Knowledge Proof can help them verify the data source. In more advanced privacy-preserving use cases, NuLink uses Fully Homomorphic Encryption to customize enterprise-level data computation services.

The Nulink technology platform consists of blockchain, access control (Proxy Re-Encryption, Attribute-Based Encryption) and secure computation (Zero-Knowledge Proof, Secure Multi-party Computation, Fully Homomorphic Encryption) as its technical core. It provides enterprise-level data sharing and computation services.

## Solution

###  Data Availability

As a platform focused on data privacy, the first thing we need to solve is the problem of data availability. This problem is often divided into two parts: the first is how consumers can determine that the seller has the data they need before purchasing, and the second is how to verify that the data in the ciphertext state is true. 

In the NuLink network, these two problems can be solved by Zero-Knowledge Proof technology: the data owner needs to provide Zero-Knowledge Proof before data authorization. In fact, the method of proof in the ciphertext data state is consistent with that in the plaintext state, which is independent of the encryption scheme used. This provides higher flexibility for NuLink networks.

###  Data Sharing

The data sharing functionality of NuLink is realized by bridging the proxy re-encryption technology to the blockchain system. This is a feature that NuLink will deploy first, and IBE and ABE will be added to this solution later. This solution can be applied in many scenarios. 

First, Alice calls the Application Layer through APP on the IOT device, selects the proxy re-encryption service and authorizes. On Alice’s NuLink side, after receiving the authorization, the Application Layer invokes the Blockchain Layer to initiate and verify the transaction, and transfers data to the Cryptograph Layer. The Cryptograph Layer interacts with the Storage Layer to perform encryption operations and upload the encrypted data. The encrypted data obtained at this step can only be decrypted by Alice. In order to convert it into ciphertext that can be decrypted by Bob, we implement proxy re-encryption through Ursula nodes deployed by NuCypher. After re-encryption, the encrypted data will be sent to the Cryptograph Layer in Bob’s NuLink side and can be decrypted directly.

### Data Computing

The data computing functionality of NuLink will be realized by bridging the fully homomorphic encryption technology to the blockchain system in the future.

It takes advantage of the property that full homomorphic encryption can be used to calculate ciphertext, that is, the user selects the data computing service in the Application Layer. After receiving the authorization, the Cryptography Layer homomorphic encrypts and uploads the user’s data to the Storage Layer. The computing node of the Blockchain Layer will access the data and perform the specified calculation (such as machine learning model prediction, etc.). Finally, the ciphertext result is returned to the Storage Layer, and the Cryptography Layer accesses the ciphertext result, which is decrypted and returned to the user. We will add MPC (multi-party computation) to this solution later.

## Architecture

The NuLink network integrates the Application Layer, the Cryptography Layer, the Storage Layer, the Blockchain Layer and the Watcher Network.

![image](./miscellaneous/img/architecture.png)

1. The Application Layer: The Application Layer is an abstract interface layer that directly interacts with the application. The Application Layer also needs to interact with the Cryptograph Layer to grant authorization of the application’s privacy data.
2. The Cryptograph Layer: The Cryptograph Layer is an entity that handles cryptographic operations on behalf of the Application Layer. The cryptographic operations include key generation, encryption, decryption, etc. The Cryptograph Layer also needs to connect to the Storage Layer and is responsible for uploading and downloading the encrypted privacy data.
3. The Storage Layer: The Storage Layer is a storage network that can be used to store encrypted privacy data. Currently, we support IPFS (InterPlanetary File System) as our decentralized storage network. Other storage networks such as Swarm and S3 will be available soon.
4. The Blockchain Layer: The Blockchain Layer is the blockchain system that can handle the proxy registration and re-encryption request management. Currently, proxies can register in Ethereum only. However, the user could send their requests to other blockchain systems such as Polkadot and Solana.
5. The Watcher Network: The Watcher Network is a relayer network that relays the information of proxy nodes from Ethereum to other blockchain systems. The Watcher Network will be maintained under an on-chain governance mechanism (DAO) to guarantee its decentralization and security.






