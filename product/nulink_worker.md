# NuLink Worker

## Minimum System Requirements
Debian/Ubuntu (Recommended)

20GB avaliable storage

4GB RAM

x86 architecture

Static IP address

Exposed TCP port 9151

Nodes can be run on cloud infrastructure.

## Install NuLink Worker

See [NuLink Worker Install](./worker_install.md). There is the option of using Docker (recommended) or a local installation.


## Bond Operator

The Staking Provider must be bonded to an Operator address. The Operator address is the ETH account that will be used when running the NuLink worker node.

- Navigate to [https://stake.nulink.org](https://stake.nulink.org)
- Connect with the Staking Provider account to execute the bond operation
- Enter the Operator address to bond
- Click “Bond Operator”

More operation see [NuLink Staking DApp](./staking_Dapp.md).

After completing the above operations, NuLink worker node will send the transaction to the corresponding network and wait for the transaction to be confirmed, so your stacking provider account must have the tokens on the corresponding chain

## Configure and Run a Worker Node

See [NuLink Worker Initialization and Running](./worker_running.md). There is the option of using Docker (recommended) or a local installation.

