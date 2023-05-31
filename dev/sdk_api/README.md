NuLink SDK / [Modules](modules.md)

# NuLink SDK

<p align="center">
  <a href="https://www.nulink.org/"><img src="https://github.com/NuLink-network/nulink-resource/blob/94c5538a5fdc25e7d4391f4f2e4af60b3c480fc1/logo/nulink-bg-1.png" width=40%  /></a>
</p><p align="center">
  <a href="https://github.com/NuLink-network"><img src="https://img.shields.io/badge/Playground-NuLink_Network-brightgreen?logo=Parity%20Substrate" /></a>
  <a href="http://nulink.org/"><img src="https://img.shields.io/badge/made%20by-NuLink%20Foundation-blue.svg?style=flat-square" /></a>
  <a href="https://github.com/NuLink-network/nulink-sdk"><img src="https://img.shields.io/badge/project-Nulink_SDK-yellow.svg?style=flat-square" /></a>
</p>NuLink SDK is a software development kit designed to support privacy computing in the NuLink network.

## Build & Install

### Build Source

```bash
1. Rename .env.example to .env
2. Modify config:
  // The SDK backend testnet server address. In the NuLink testnet,
  // you can use the address: https://agent.testnet.nulink.org/bk
  REACT_APP_CENTRALIZED_SERVER_URL=xxxxx
  // Your IPFS address, requires permission to write data. In the NuLink testnet,
  // you can use the address: https://agent.testnet.nulink.org/nuipfs
  REACT_APP_IPFS_NODE_URL=xxxxx
  // The NuLink porter address. In the NuLink testnet,
  // you can use the address: https://agent.testnet.nulink.org/porter
  REACT_APP_PORTER_URL= xxxxx
  // The BSC testnet Web3 RPC URL. Example:
  REACT_APP_WEB3_RPC_URL=xxxxx

3. yarn install
4. yarn build:main
```
### Install via npm

```bash
npm i @nulink_network/nulink-sdk
```
or
```bash
yarn add @nulink_network/nulink-sdk
```

## API docs

### The Classes
* `NulinkHDWallet`: The module mainly includes interfaces for nulink wallet related operations.
* `AccountManager`: The module mainly responsible for managing multiple Account objects. AccountManager is a property of the NulinkHDWallet wallet object.
* `Account`: The module mainly includes interfaces for nulink wallet account related operations. Account is a property of the AccountManager object.
* `Strategy`: The module is mainly used to encrypt user files for file uploading using private keys.

### The Functions
* `Functions`: The module mainly includes interfaces for file encryption and uploading, as well as operations related to interacting with the blockchain.

<!--[API](./docs/modules.md) -->
[API Details](./modules.md)


## Usage Example

