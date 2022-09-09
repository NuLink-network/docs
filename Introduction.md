# Introduction


NuLink network is a decentralized solution for privacy-preserving applications developers to implement best practices and best of breed security and privacy. The NuLink network  provides endpoint encryption and cryptographic access control. Sensitive user data can be securely shared from any user platform to cloud or decentralized storage and access to that data is granted automatically by policy in Proxy Re-Encryption or Attribute-Based Encryption. For the data user on the other side, Zero-Knowledge Proof can help them verify the data source. In more advanced privacy-preserving use cases, NuLink uses Fully Homomorphic Encryption to customize enterprise-level data computation services.

The Nulink technology platform consists of blockchain, access control (Proxy Re-Encryption, Attribute-Based Encryption) and secure computation (Zero-Knowledge Proof, Secure Multi-party Computation, Fully Homomorphic Encryption) as its technical core. It provides enterprise-level data sharing and computation services.

## Architecture

The NuLink network integrates the Application Layer, the Cryptography Layer, the Storage Layer, the Blockchain Layer and the Watcher Network.

![image](./Miscellaneous/img/architecture.png)

1. The Application Layer: The Application Layer is an abstract interface layer that directly interacts with the application. The Application Layer also needs to interact with the Cryptograph Layer to grant authorization of the application’s privacy data.
2. The Cryptograph Layer: The Cryptograph Layer is an entity that handles cryptographic operations on behalf of the Application Layer. The cryptographic operations include key generation, encryption, decryption, etc. The Cryptograph Layer also needs to connect to the Storage Layer and is responsible for uploading and downloading the encrypted privacy data.
3. The Storage Layer: The Storage Layer is a storage network that can be used to store encrypted privacy data. Currently, we support IPFS (InterPlanetary File System) as our decentralized storage network. Other storage networks such as Swarm and S3 will be available soon.
4. The Blockchain Layer: The Blockchain Layer is the blockchain system that can handle the proxy registration and re-encryption request management. Currently, proxies can register in Ethereum only. However, the user could send their requests to other blockchain systems such as Polkadot and Solana.
5. The Watcher Network: The Watcher Network is a relayer network that relays the information of proxy nodes from Ethereum to other blockchain systems. The Watcher Network will be maintained under an on-chain governance mechanism (DAO) to guarantee its decentralization and security.







