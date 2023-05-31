# Frequently Asked Questions

## General

**Q: What is NuLink?**  
NuLink network is a decentralized solution for privacy-preserving applications developers to implement best practices and best of breed security and privacy. The NuLink network provides endpoint encryption and cryptographic access control. Sensitive user data can be securely shared from any user platform to cloud or decentralized storage and access to that data is granted automatically by policy in Proxy Re-Encryption or Attribute-Based Encryption. For the data user on the other side, Zero-Knowledge Proof can help them verify the data source. In more advanced privacy-preserving use cases, NuLink uses Fully Homomorphic Encryption to customize enterprise-level data computation services.

**Q: What problems does NuLink solve and how?**  
Today it is complicated(sometimes expensive) to implement security and encryption of personal data. NuLink want to offer an out of box encryption solution that makes it easy to implement best practice, modern and up to data security. The solution will offer everything needed including data encryption, key and storage management, inter-blockchain deployment and much more.  

**Q: How is NuLink different from other privacy networks?**  
NuLink network is an algorithm-based solution to protect the privacy data. We provide a combination of cryptography technologies(such as PRE, IBE/ABE, ZKP, FHE) to solve 3 parts of privacy data issues: data availability, privacy data sharing, and privacy data computing. 

## NuLink Product

**Q: What is the difference between NuLink Agent, NuLink Agent SDK and NuLink SDK?** 

The NuLink Applicaiton Layer consists of three main components: NuLink Agent, NuLink Agent SDK, and NuLink SDK. Here's a summary of their differences:

* NuLink Agent: NuLink Agent is a web-based digital wallet that acts as an intermediary between applications and the NuLink network. Its primary function is to facilitate seamless communication and interaction between the two. It relays requests and responses between applications and the underlying layers of the NuLink network. Users can use NuLink Agent to securely manage their digital assets and perform transactions on the NuLink network.

* NuLink Agent SDK:The NuLink Agent SDK is a set of software development tools and resources provided to developers. It empowers developers to integrate the functionality of NuLink Agent into their own applications. By using the NuLink Agent SDK, developers can enable secure and efficient communication with the NuLink network within their applications. It allows developers to leverage the capabilities of NuLink Agent, such as managing digital assets and performing transactions, while customizing the user experience according to their application's requirements.

* NuLink SDK: The NuLink SDK is a comprehensive software development kit that offers developers a wide range of capabilities. It allows developers to establish flexible connections with the NuLink network and interact with it seamlessly. The NuLink SDK provides advanced cryptographic operations and functionalities, enabling developers to leverage the full potential of the NuLink ecosystem. It allows developers to build applications that ensure enhanced security and privacy through the utilization of advanced cryptographic techniques. It's important to note that the NuLink Agent is implemented using the NuLink SDK, meaning that the Agent harnesses the powerful features of the NuLink SDK to facilitate secure communication and interaction between applications and the NuLink network.

In summary, NuLink Agent is the web-based digital wallet that facilitates communication with the NuLink network, NuLink Agent SDK provides tools for developers to integrate NuLink Agent functionality into their applications, and NuLink SDK is a comprehensive toolkit that enables developers to establish flexible connections, perform cryptographic operations, and interact with the NuLink network. 

**Q: I am a Dapp developer, how can I intergrate NuLink Agent into my Dapp?** 

To integrate NuLink Agent into your Dapp, you can follow these steps:

* Install and import NuLink Agent SDK: Start by installing and import the NuLink Agent SDK in your project. This will provide you with the tools and resources needed to interact with NuLink Agent. You can refer to the [documentation](../dev/agent_sdk.md) provided with the Agent SDK for detailed installation instructions specific to your development environment.

* Set up NuLink Agent connection: Use the SDK to establish a connection between your Dapp and NuLink Agent. This connection will allow you to send requests and receive responses from the NuLink network.

* Implement callback functions: In order to handle responses and execute actions after the corresponding methods are successfully executed, you can define and implement callback functions. The NuLink Agent SDK provides a list of supported callback functions that you can use.

By integrating the NuLink Agent SDK and implementing the appropriate callback functions, you can seamlessly integrate NuLink Agent functionality into your Dapp and enable secure and efficient communication with the NuLink network.

## Horus Testnet

**Q: Is Horus testnet a blockchain ?**  
No, Horus testnet is an independent network which deployed in BNB testnet. It includes five parts: a cryptographic service provider network constructed by many worker nodes; a bundle of smart contracts in BNB testnet which used to incentive the worker nodes; a Dapp for user to manage his worker nodes and interact with the smart contracts; an agent to handle the local cryptographic operations; a Dapp for user to deal with the privacy file sharing service provided by the worker nodes. 