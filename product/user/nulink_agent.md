# NuLink Agent

## What is NuLink Agent?
NuLink Agent is a web-based digital wallet that differs from traditional plugin wallets in that it does not need to be installed on the browser. 
Instead, users can simply open a webpage and login to manage their NuLink private account data and digital assets, as well as interact with other DApps.

When browsing third-party DApps, if the application supports NuLink account authorization login, users can launch the NuLink Agent authorization login page for logging in. After logging in to the NuLink Agent account, users can perform a series of on-chain operations such as applying for fund account authorization, transferring funds, uploading files, and more. All of these operations will be recorded on the blockchain.

## Access NuLink Agent

* [NuLink Agent for Testnet](https://agent.testnet.nulink.org)
* NuLink Agent for Mainnet (In development...)

## Registration

Open NuLink Agent [https://agent.testnet.nulink.org ](https://agent.testnet.nulink.org) or https://agent.nulink.org (in development). 

If you are a new user, you need to register by clicking `CREATE AN AGENT ACCOUNT` and proceed to the next step.

![Create Account](../../miscellaneous/img/agent/create.png)

Enter the password setting page, where the password needs to be entered twice for confirmation.
Make sure you can remember the password, which will be used to verify your identity during certain account security operations.

![Set Password](../../miscellaneous/img/agent/password.png)

## Backup Mnemonic

After registration, it is essential to back up your mnemonic. The mnemonic is used to restore your account. Even if you change your computer, you can recover your account as long as you have your mnemonic.

After registration, it is essential to back up your mnemonics. The mnemonics are used to recover your account. Even if you switch computers, as long as you have the mnemonic phrase, you can retrieve your account. 
Click `Start backing up` to proceed.

![Backup Mnemonic](../../miscellaneous/img/agent/backup.png)

Here is your mnemonic phrases. You can click `Copy` to copy it to your computer, but it's best to handwrite it in your notebook to prevent accidental deletion or loss.

![Display Mnemonic](../../miscellaneous/img/agent/mnemonics.png)

Finally, to ensure you have saved the mnemonic phrase correctly, verify the accuracy of the saved phrase by writing the corresponding words as prompted. 
A successful verification message will appear upon completion.

![Verify Mnemonic](../../miscellaneous/img/agent/verify.png)


## Account Recovery

If you already have an account and have saved your mnemonic phrases, you can directly click `RESTORE YOUR ACCOUNT` on the "Home" page. 
Enter your mnemonic phrases and reset your password to successfully recover and log into your account.

![Restore Account](../../miscellaneous/img/agent/restore.png)


## Homepage

After registering or recovering your account, the page will automatically redirect to the account homepage, where you can see all your token balances. 
Currently, two types of tokens are supported: NLK and BNB. You can also view each of your transaction records.

![Homepage](../../miscellaneous/img/agent/main.png)

## Transfer

After selecting the Token, click `Send` to enter the transfer page. 
Enter the "Receiver's address" and "Amount". You can also click `Max` to transfer all balances. 
After confirming the information, click `Next` to complete the transfer. A certain amount of gas fees will be charged for each transaction.

![Transfer](../../miscellaneous/img/agent/transfer.png)

## Receive

Click `Receive` to display your account address and a QR code. The QR code contains your account address, which is convenient for others to scan and transfer without manual input.

![Receive](../../miscellaneous/img/agent/receive.png)

## Settings

Click `Setting`, switch to `Setup Network`. 
The system has preset the RPC URL. If you have a faster RPC URL, you can set it yourself for a better experience.

![Setting](../../miscellaneous/img/agent/setting.png)

## Export Private Key
The private key contains all account information. The purpose of exporting the private key is to enable users to view their account information in other wallets. For example, users can import the private key of NuLink Agent to MetaMask to view their account information on NuLink Agent.

The private key contains all account information. The purpose of exporting the private key is to enable users to view their account information in other wallets. 
For example, you can view your NuLink Agent account information on Metamask by importing the NuLink Agent's private key.

![Export Private Keys](../../miscellaneous/img/agent/export.png)

Read the security tips carefully to ensure privacy during the export process.
Click `EXPORT PRIVATE KEYS`, enter your account password, and you can view your private key.

![Enter Password](../../miscellaneous/img/agent/enter_password.png)

After obtaining the private key, click `COPY PRIVATE KEYS` below to quickly copy your private key. 
Follow the security tips below to keep your private key safe.

![Export Private Keys](../../miscellaneous/img/agent/exported.png)
