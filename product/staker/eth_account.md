# Create Worker Account Using Geth

There are several ways to install Geth, including through the package manager, downloading the pre-built package, running as a docker container, or building from the downloaded source code. Please refer  [here](https://geth.ethereum.org/docs/install-and-build/installing-geth) for more details regarding Geth Installation.

After installing Geth, it will save the keystore file to the local storage. Please remember the keystore file path and account address for later use.

## Example on Ubuntu

This section will demonstrate how to generate a Worker account using the official build package provided by Ethereum on Ubuntu.


1. Download [Geth](https://geth.ethereum.org/downloads/), select the installation packages of various versions applicable to different systems.
```shell
wget https://gethstore.blob.core.windows.net/builds/geth-linux-amd64-1.10.23-d901d853.tar.gz
```
2. Unzip the downloaded installation package
```shell
tar -xvzf geth-linux-amd64-1.10.23-d901d853.tar.gz
```
3. Enter the unzipped directory
```shell
cd geth-linux-amd64-1.10.23-d901d853/
```
4. Use. / get account new -- keystore. / keystore to generate Ethereum account and keystore
```shell
./geth account new --keystore ./keystore
```
5. You will be prompted to enter the password and confirm the password. **Please remember this password for late use.**

Example：

```shell
INFO [09-08|15:30:11.904] Maximum peer count                       ETH=50 LES=0 total=50
INFO [09-08|15:30:11.905] Smartcard socket not found, disabling    err="stat /run/pcscd/pcscd.comm: no such file or directory"
Your new account is locked with a password. Please give a password. Do not forget this password.
Password: 
Repeat password: 

Your new key was generated


Public address of the key:   0x8B1819341BEc211a45a2186C4D0030681cccE0Ee
Path of the secret key file: /root/geth-linux-amd64-1.10.23-d901d853/keystore/UTC--2022-09-13T01-14-32.465358210Z--8b1819341bec211a45a2186c4d0030681ccce0ee

- You can share your public address with anyone. Others need it to interact with you.
- You must NEVER share the secret key with anyone! The key controls access to your funds!
- You must BACKUP your key file! Without the key, it's impossible to access account funds!
- You must REMEMBER your password! Without the password, it's impossible to decrypt the key!
```



