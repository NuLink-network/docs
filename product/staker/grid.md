# My Staking Grids

This page shows all the staking grids you own, which are categorized into two statuses: 
`Installed` and `Uninstalled`.

![My Staking Grids List](../../miscellaneous/img/dashboard/gridList.png)

The list displays all installed storage grids, where you can see the node-related information and staking overview for each grid.

## Install Grid

### BOND WORKER
Before a grid is officially open for staking, you need to `BOND WORKER` and start the node, 
as shown in the image below:

![Bond Worker](../../miscellaneous/img/dashboard/workerBond.png)

If you’re unsure how to start the node, please click to view the help manual.

### Stake Grid Details
Click `EDIT STAKE GRID` to view the grid’s details and staking overview. 

![Edit Grid Details](../../miscellaneous/img/dashboard/gridDetail.png)

* Click `DETECT CURRENT STATUS`, if successful will return an `Online` status, otherwise `Offline`.
* 
* Click `UNBOND WORKER`, a pop-up will appear. Confirm to unbond the worker successfully.

![Unbond Worker](../../miscellaneous/img/dashboard/workerUnbond.png)

* Click `CHANGE WORKER`, and a pop-up will appear. Enter the new address and submit to successfully change the worker.
  
![Change Worker Address](../../miscellaneous/img/dashboard/workerChange.png)

* Click `EDIT INFO` to edit the grid’s description and social media content.

![Edit Grid Info](../../miscellaneous/img/dashboard/gridEdit.png)

Scrolling down in the Stake Grid Details page, you can see the staking overview for the current period:

![Staking Grid Details](../../miscellaneous/img/dashboard/gridStakeDetail.png)

* `VALID STAKING AMOUNT`: TOTAL STAKING AMOUNT * LIVING RATIO
* `VALID STAKING QUOTA`: VALID STAKING AMOUNT / Platform-wide VALID STAKING AMOUNT
* `STAKING REWARD`: VALID STAKING QUOTA * Platform Total Reward
* `LIVING RATIO`: This parameter measures the uptime of the node (the higher the value, the higher the rewards).


Click `EDIT EPOCH FEE` to customize the fee for the epoch, as shown in the image below:

![Edit Epoch Fee](../../miscellaneous/img/dashboard/gridFee.png)

Scrolling further down, you can see all staking records under the grid.

![Grid Staking Records](../../miscellaneous/img/dashboard/gridRecords.png)

## Uninstalled
   
This list shows all uninstalled grids, allowing you to install or transfer them. 

![Grid Uninstalled](../../miscellaneous/img/dashboard/gridUninstalled.png)

Click `INSTALL STAKE GRID` to display the pop-up below. Set the fee and submit to complete the installation.

![Enter the Staking Fee](../../miscellaneous/img/dashboard/gridInstall.png)

Click `ASSIGN TO ADDRESS` to display the pop-up below. 
Enter the recipient's address. Upon submission, the wallet will prompt for gas payment. 
Once paid, the transfer is successful.

![Assign Address](../../miscellaneous/img/dashboard/gridAssignAddress.png)


