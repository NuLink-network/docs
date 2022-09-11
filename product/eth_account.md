# Generate Ethereum Account

First of all, we need to install Geth. There are several ways to install Geth, including through the package manager, downloading the prebuilt package, running as a docker container, or building from the downloaded source code. For detailed installation instructions, please refer to [follow instructions](https://geth.ethereum.org/docs/install-and-build/installing-geth)

This document will demonstrate how to generate an Ethereum account using the official build package provided by Ethereum on Ubuntu.


1. Download [Geth](https://geth.ethereum.org/downloads/), select the installation packages of various versions applicable to different systems.
2. Unzip the downloaded installation package
3. Enter the unzipped directory
4. Use. / get account new -- keystore. / keystore to generate Ethereum account and keystore

e.g.：

```shell
# step 1
wget https://gethstore.blob.core.windows.net/builds/geth-linux-amd64-1.10.23-d901d853.tar.gz

# step 2
tar -xvzf geth-linux-amd64-1.10.23-d901d853.tar.gz

# step 3
cd geth-linux-amd64-1.10.23-d901d853/

# step 4
./geth account new --keystore ./keystore

INFO [09-08|15:30:11.904] Maximum peer count                       ETH=50 LES=0 total=50
INFO [09-08|15:30:11.905] Smartcard socket not found, disabling    err="stat /run/pcscd/pcscd.comm: no such file or directory"
Your new account is locked with a password. Please give a password. Do not forget this password.
Password: 
Repeat password: 

Your new key was generated

Public address of the key:   0x037353D1988f91aA7b7D4CBB4Bf9135887A101e6  # 账号
Path of the secret key file: /root/geth-linux-amd64-1.10.23-d901d853/keystore/UTC--2022-09-08T07-30-15.029270584Z--037353d1988f91aa7b7d4cbb4bf9135887a101e6 # keystore 文件路径

- You can share your public address with anyone. Others need it to interact with you.
- You must NEVER share the secret key with anyone! The key controls access to your funds!
- You must BACKUP your key file! Without the key, it's impossible to access account funds!
- You must REMEMBER your password! Without the password, it's impossible to decrypt the key!
```

After entering the command in step 4, you will be prompted to enter the password and confirm the password. Then the corresponding account and keystore file will be generated.