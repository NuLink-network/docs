# NuLink Agent SDK
The SDK for third-party integration with [NuLink Agent](../product/nulink_agent.md).

These APIs allow you to access NuLink Agent programmatically and perform various actions, such as connect, upload, apply, approve and download.

## Getting Started

The default address in the Nulink Web Agent Access SDK:

* NuLink Agent: https://agent.testnet.nulink.org, and the default 
* Backend service address: https://agent-integration-demo.nulink.org/bk. 

If you need to change these two addresses, you will need to write the following configurations in the .env file of your project: REACT_APP_NULINK_AGENT_ADDRESS for the web agent address and REACT_APP_NULINK_BACKEND_ADDRESS for the backend service address.

```
// modify .env in your project
// the web agent address
REACT_APP_NULINK_AGENT_ADDRESS=xxxxxx
// the agent bcakend service address
REACT_APP_NULINK_BACKEND_ADDRESS=xxxxxx
```

## Install
```bash
npm i @nulink_network/nulink-web-agent-access-sdk
```
or
```bash
yarn add @nulink_network/nulink-web-agent-access-sdk
```

## How to use

See [Agent SDK example](./agent_example.md) to get how to use NuLink Agent SDK.

Here the [Agent SDK API reference](./agent_api.md).
