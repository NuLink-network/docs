
# NuLink SDK

NuLink SDK is a software development kit designed to support privacy computing in the NuLink network.

## Build & Install

### <a id="BuildSource">Build Source</a>

#### Set up your environment

1. select a configuration file of your usage environment

- Development Environment (.env.dev)
- Production Environment (.env.prod)
- Custom Environment (.env.example)

2. Rename configuration file to .env

- for Development Environment: rename .env.dev to .env
- for Production Environment: rename .env.prod to .env
- for Custom Environment: rename .env.example to .env, [then you need to modify the configuration file manually](#customEnvConfig)

##### <a id="customEnvConfig">Set configuration for a custom environment </a>

```javascript
//Modify config:
//the sdk backend testnet server address. in the nulink testnet,
//you can use the address: https://agent.testnet.nulink.org/bk
REACT_APP_CENTRALIZED_SERVER_URL=xxxxx

//Configure the parameters of the network that you connect to. Parameters for networks that are not connected do not need to be configured.

//the nulink bsc testnet porter address. in the nulink testnet,
//you can use the address: https://agent.testnet.nulink.org/porter
REACT_APP_BSC_TESTNET_PORTER_URI= xxxxx
//the network's (e.g. bsc testnet) web3 rpc url. example:
REACT_APP_BSC_TESTNET_WEB3_RPC_URL=xxxxx
```

#### build project

```shell
1. yarn install
2. yarn build:main
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

[API Details](./modules.md)


## Usage Example

See [NuLink SDK Examples](./sdk_example.md)  to get how to use NuLink SDK.
