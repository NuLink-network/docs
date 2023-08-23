# NuLink Staking Dapp

## Overview
Nulink Staking Dapp is a platform for managing the staker/worker account. Users could log in his staking account through the Metamask wallet, stake NLKs(test), and bind Woker account to get the reward. You can access Nulink Staking Dapp through this [link](https://www.nulink.org).

In order to use NuLink Staking Dapp for the Horus network, the user needs to get the initial fund of NLKs(test) and BNBs(test) on [faucet](https://www.nulink.org). 



## Work Flow
![image](../miscellaneous/img/stakeflow.png)  

### Step1- Initialization: Connect Wallet and Log in staking account

NuLink currently supports only METAMASK wallet. Users need to [download](https://metamask.io/download/) and install METAMASK wallet ahead. If you need more help with METAMASK usage, please refer [here](https://metamask.io/faqs/). Please create an account for staking in METAMASK after installation. 

Once create a staking account in METAMASK  wallet, login and connect the staking account in [Nulink Staking Dapp](https://test-staking.nulink.org). Click the "Connect Wallet" at the top right corner of the page, and a pop-up window connecting to METAMASK wallet will appear. Click the "Connect Wallet " in the pop-up window, and the METAMASK wallet plug-in will be invoked.  

![image](../miscellaneous/img/connectWallet.png)  

After connecting with METAMASK Wallet, the system will automatically detect whether you connect to the Horus network. If not, it automatically prompts a window for you to switch to the correct network.  

![image](../miscellaneous/img/networkError.png)  

**Remark:** The default RPC server for BSC testnet sometime is unstable. If you find the current server is done, please find an active one [here](https://chainlist.org/)  and replace it in METAMASK network setting. Need [help](https://metamask.zendesk.com/hc/en-us/articles/4404424659995-User-Guide-Custom-networks-and-sidechains) editing RPC server in METAMASK?

### Step2- Stake NLKs(test) to the staking pool
Once log in with METAMASK wallet, please check the balance and click the "Staking" button to stake tokens to the staking pool. Make sure claim](https://test-staking.nulink.org/faucet) enough NLKs(test) and BNBs(test) in the staking account as initial funds. Remember bonding an active worker after staking, otherwise no reward will be issued. 

![image](../miscellaneous/img/staking.png)  

### Step3- Bond an active worker to gain reward.
An active Worker node is needed before clicking "Bond Worker". Please refer [here](nulink_worker.md) for running a Worker. The Bond Worker page will  pop-up when click "Bond Worker".  Simply enter the Worker Address and Node URI, and then confirm the bonding. Now the whole staking process is completed and the reward NLKs(test) will be issued.

![image](../miscellaneous/img/bondWorker2.png)  

### Step4- Stop staking and quit.

Follow the checklist below to stop the staking and get all funds along with reward:
* Unbound Worker and shut down the Worker node
* Unstake your fund from staking pool
* Claim reward

#### How to unbound Worker and shut down the Worker node?
Click  “Unbound worker ". It will prompt a window to confirm unbond operation. 

Remark: There is a bond lock time(24 hours) for the Horus network, which means the user can not unbond within 24 hours after bonding Worker.

 ![image](../miscellaneous/img/unbondWorker1.png)  

After unbonding Worker, the Worker node is free to closed.

#### How to unstake?
Click the "Unstake" pop-up a  window to prompt whether to unstake. The staking will be released after confirming.

 ![image](../miscellaneous/img/unstake.png)  

#### How to withdraw your reward?
Click "Claim" to withdraw the reward after unstaking fund.

 ![image](../miscellaneous/img/claim.png)  

### Transaction Notification

For all the above operation, the Dapp will send a corresponding transaction on BSC testnet.  Click the bell in the right up corner to view the notice list. Click ’View details‘ to see details of each transaction massage.  


 ![image](../miscellaneous/img/messages.png)  

## Term Explaination in Dapp.

1.  **Total Value Locked**: Total lock-in value of the Horus network.  
2.  **Total Nodes**: Total number of Worker nodes in the Horus network.  
3.  **My Balance**: Current balance in user's account, can be used for staking to pool.   
4.  **Reward**: Unclaimed reward of the user's account.    
5.  **My Node Info**: Displays user node details, including the following data:  
      * Node URI: IP and Port of users’ Worker node.
      * Worker Status: The current status of user's Worker node. Either online or offline.
      * Staker Address: Address of the user's staking account.
      * Woker Address: Address of the user's Worker node.
      * Start time:  The time start to earn reward(finish staking and bonding), accurate to second.
      * Accumulated time:  Accumulated time for earning reward, accurate to second.
      * Reward: Unclaimed rewards for the user .
      * Staking Amount: The amount of fund which user stake in the pool.
6.  **Node List**: Displays all active nodes in the Horus network, including the following data:   
      * Node URI: IP and Port of the Worker node.
      * Staker Address: Address of the node's staking account.
      * Woker Address: Address of the node's Worker node.
      * Worker Status: The current status of user's Worker node. Either online or offline.
    
