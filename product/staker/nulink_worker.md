# NuLink Worker

## Overview  

The NuLink Worker is the node to provide cryptographic service in the NuLink network. It provides Proxy Re-encryption service in the Horus network and it will provide more services such as ABE, IBE, ZKP and FHE in NuLink mainnet. The staker needs running a Worker node to be eligible for token reward. 

There are four steps to run a NuLink Worker:
1. Create Worker Account
2. Bond the Worker Account with your staking account
3. Install NuLink Worker
4. Configure and Run a Worker node

**Warning:** Do not use same address for staker account and worker account. Make sure to generate a new one for worker account.

## Minimum System Requirements  

* Debian/Ubuntu (Recommended)
* 30GB available storage
* 4GB RAM
* x86 architecture
* **Static IP address**
* **Exposed TCP port 9151, make sure it's not occupied**
* Nodes can be run on cloud infrastructure.

## Create Worker Account  

Prepare an ETH type account for the Worker. We suggest creating a Worker account different from the staking account. 

If you already know how to create one and access the keystore file, you can skip this step. Otherwise we recommend you to use Geth to create the Worker account.  Please check [here](./eth_account.md) for details.

## Bond the Worker Account with your staking account  

Don't forget to bond it with your staking account to get reward after successfully running a NuLink Worker node using the NuLink Staking Dashboard. 

- Navigate to [NuLink Staking Dashboard](https://dashboard.testnet.nulink.org)
- Connect with the Staking account and make sure you have staked tokens in the staking pool
- Enter the Worker address to bond
- Click “Bond Worker”

## Install NuLink Worker  

Start to download and install NuLink Worker.  Install it using Docker (recommended) or install it with local installation. See [here](./worker_install.md) for more details. 

## Initialize and Run a Worker Node  

Initialize the configuration and start the Worker Node. If install via docker, need to initialize the configuration and run it in Docker. Otherwise please check  [here](./worker_running.md) for more details regarding local running. 



Refer [here](./dashboard.md) for more usage of NuLink Staking Dashboard.




