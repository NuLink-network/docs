# NuLink Worker Initialization and Running  


After installing the worker node via Docker, you can initialize and run it by following these three steps:
1. **Export Node Environment Variables**
2. **Initialize Node Configuration**
3. **Launch the Node**


**You have to deposit a small amount of the testnet BNB (tBNB) into the worker account to facilitate the sending of a confirmation transaction.**




## Export Node Environment Variables  
To streamline the Docker installation procedure, we utilize certain environment variables. These variables are crucial for the operation of the NuLink Worker.

Select a password with at least 8 characters to lock and unlock the private storage created by the NuLink Worker. **It's important to remember this password for future access.**
```shell
export NULINK_KEYSTORE_PASSWORD=<YOUR NULINK STORAGE PASSWORD>
```
This password is used to unlock the keystore file of your Worker account. You would have established this password when creating the Worker account via Geth. Make sure you enter the same one!!!
```shell
export NULINK_OPERATOR_ETH_PASSWORD=<YOUR WORKER ACCOUNT PASSWORD>
```

## Initialize Node Configuration  
This step creates and stores the NuLink worker node configuration, and only needs to be run once.

```shell
$ docker run -it --rm \
-p 9151:9151 \
-v </path/to/host/machine/directory>:/code \
-v </path/to/host/machine/directory>:/home/circleci/.local/share/nulink \
-e NULINK_KEYSTORE_PASSWORD \
nulink/nulink nulink ursula init \
--signer <ETH KEYSTORE URI> \
--eth-provider <NULINK PROVIDER URI>  \
--network <NULINK NETWORK NAME> \
--payment-provider <PAYMENT PROVIDER URI> \
--payment-network <PAYMENT NETWORK NAME> \
--operator-address <WORKER ADDRESS> \
--max-gas-price <GWEI>
```
Replace the following values with your own value:
- `</path/to/host/machine/directory>` - The host directory you create when install.
- `<ETH KEYSTORE URI>` - The path to the keystore file of the Worker account.
- `<NULINK PROVIDER URI>` - The URI of a local or hosted node where the Horus network launched.
- `<NULINK NETWORK NAME>` - The name of the network where  the Horus network launched. 
- `<PAYMENT PROVIDER URI>` - The URI of a local or hosted node where payment goes.
- `<PAYMENT NETWORK NAME>` - The name of the payment network. 
- `<OPERATOR ADDRESS>` - The address of the Worker account. [How to generate Worker account](./eth_account.md).
- `<GWEI>` (Optional) - The maximum price of gas to spend on any transaction.

Example Input:

```shell
docker run -it --rm \
-p 9151:9151 \
-v /root/nulink:/code \
-v /root/nulink:/home/circleci/.local/share/nulink \
-e NULINK_KEYSTORE_PASSWORD \
nulink/nulink nulink ursula init \
--signer keystore:///code/UTC--2022-09-13T01-14-32.465358210Z--8b1819341bec211a45a2186c4d0030681ccce0ee \
--eth-provider https://data-seed-prebsc-2-s2.binance.org:8545 \
--network horus \
--payment-provider https://data-seed-prebsc-2-s2.binance.org:8545 \
--payment-network bsc_testnet \
--operator-address 0x8B1819341BEc211a45a2186C4D0030681cccE0Ee \
--max-gas-price 10000000000
```
Example Output:

```shell
# step 1
 Detected IPv4 address (8.219.186.125) - Is this the public-facing address of Ursula? [y/N]: y
 
 Please provide a password to lock Operator keys.
 Do not forget this password, and ideally store it using a password manager.
 
 # step 2
 Enter nulink keystore password (8 character minimum): xxxxxx
 Repeat for confirmation: xxxxxx
 
 Backup your seed words, you will not be able to view them again.
 
 xxxxxxxxxxxxxxxxxxxxxxxx
 
 # step 3
 Have you backed up your seed phrase? [y/N]: y
 
 # step 4
 Confirm seed words: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
 
 
Public Key:   02bb2067d21a677ce928967c0ece79a9
Path to Keystore: /home/circleci/.local/share/nulink/keystore

- You can share your public key with anyone. Others need it to interact with you.
- Never share secret keys with anyone! 
- Backup your keystore! Character keys are required to interact with the protocol!
- Remember your password! Without the password, it's impossible to decrypt the key!


Generated configuration file at default filepath /home/circleci/.local/share/nulink/ursula.json

* Review configuration  -> nulink ursula config
* Start working         -> nulink ursula run

```

## Launch the Node  
Before performing this step, make sure that the environment variable has been set successfully.
You can verify it using the following method, execute the following command: 
```shell

root@xxx:~#echo $NULINK_KEYSTORE_PASSWORD
12345678
root@xxx:~#echo $NULINK_OPERATOR_ETH_PASSWORD
12345678
```

If the password is not displayed, please reset the environment variables.
```shell
export NULINK_KEYSTORE_PASSWORD=<YOUR NULINK STORAGE PASSWORD>
export NULINK_OPERATOR_ETH_PASSWORD=<YOUR WORKER ACCOUNT PASSWORD>
```

The following command will start the node. Make sure you use the same host directory as the configuration. 

**Remark1: You need to [claim](https://testnet.binance.org/faucet-smart) some BNB(test) token for Worker account as gas fee.**

**Remark2: If you encounter error when starting Worker node,  first please check that the port 9151 has not been occupied by other process. If still not working, please check there is only one configuration json file in the </path/to/host/machine/directory>**

```shell
$ docker run --restart on-failure -d \
--name ursula \
-p 9151:9151 \
-v </path/to/host/machine/directory>:/code \
-v </path/to/host/machine/directory>:/home/circleci/.local/share/nulink \
-e NULINK_KEYSTORE_PASSWORD \
-e NULINK_OPERATOR_ETH_PASSWORD \
nulink/nulink nulink ursula run --no-block-until-ready
```

Example Input：
```shell
docker run --restart on-failure -d \
--name ursula \
-p 9151:9151 \
-v /root/nulink:/code \
-v /root/nulink:/home/circleci/.local/share/nulink \
-e NULINK_KEYSTORE_PASSWORD \
-e NULINK_OPERATOR_ETH_PASSWORD \
nulink/nulink nulink ursula run --no-block-until-ready
```
Example Output:

```shell
aa3a0f6376b566473cbcde46b0e772feb4d3658188d2cbb424a1e94588d6d8eb
```




## Check Node Status for Worker Account
The following command describes how to view worker status.

```shell
docker logs -f <docker name>
```
Example Input:
```shell
docker logs -f ursula
```
Example Output:
```shell
Authenticating Ursula
Loaded Ursula (horus)
✓ External IP matches configuration
Starting services
✓ Node Discovery (Horus)
✓ Work Tracking
✓ Start Operator Bonded Tracker
✓ Rest Server https://8.219.186.125:9151
Working ~ Keep Ursula Online!

```

Now the Worker address(e.g: 0x8B1819341BEc211a45a2186C4D0030681cccE0Ee)  is ready for bonding operation.

## Restart the Worker Node

Occasionally, the staker may find it necessary to restart the worker node. Below is the command for restarting the currently running nodes:

```shell
docker restart <container ID>
```
