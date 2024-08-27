
# NuLink SDK Examples

## Usage

### <a id="SwitchNetworks">SelectNetworks</a>

When nulink supports multiple networks, users can set their preferred network using the following method:

```javascript

import {setCurrentNetworkKey} from "@nulink_network/nulink-sdk";

 //The currently available network: NETWORK_LIST.Horus
await setCurrentNetworkKey(NETWORK_LIST.Horus)

```

### <a id="SetDataStorage">Set Data Storage</a>

Since the purpose of nulink pre is to encrypt and share data (files), it inevitably involves uploading (storing) and downloading (retrieving) files. Therefore, it is necessary to set up the methods for accessing files. The process is as follows:

first, we need to import package

```javascript

import {
  StorageManager,
  DataCallback,
  setIPFSData,
  getIPFSData,
} from '@nulink_network/nulink-sdk'
```

Then, you need to implement the <b>setData</b> and <b>getData</b> methods of the DataCallback structure.
Since we need to upload data (files) in batches in our use case, while usually retrieving them one by one, we need to implement the <b>setData</b> method for batch uploading and the <b>getData</b> method for retrieving data individually.

```javascript

const dataCallback: DataCallback = { setData: setIPFSData, getData: getIPFSData }
  //Set the external storage used by the Pre process to IPFS (for example, encrypted files uploaded by users will be stored in this storage, and users can customize the storage).
  StorageManager.setDataCallback(dataCallback)

```

After setting up the callback functions, when we upload files using the uploadDataByCreatePolicy method in pre, the callback function <b>setData</b> you have set will be automatically invoked. Later, when we retrieve files using getDataContentAsUser, the <b>getData</b> function will be automatically called.

The <b>setData</b> and <b>getData</b> types are as follows:

```javascript

export type DataCallback = {
    setData: AsyncSetDataCallback;
    getData: AsyncGetDataCallback;
};

export type AsyncSetDataCallback = ((data: DataType, account: Account) => Promise<string[]>) | ((data: DataType) => Promise<string[]>);

export type AsyncGetDataCallback = (key: string) => Promise<Buffer | Uint8Array | null | undefined>;

```

<b>Notes</b>:

    Please note that the Account parameter is optional. If the setData callback function defined by the user requires account information (such as signing data with the account's private key), the callback function can be defined with an additional parameter for the account. In the pre process, when the setData callback function is called, the account information will be passed to the user-defined callback function, allowing the callback function to access the current account information (account parameter).

<b>More details</b>:

For more information, you can refer to this example: [upload.backend.ts](https://github.com/NuLink-network/nulink-sdk/blob/crosschain/src/core/utils/external-storage/implement/upload.backend.ts)

If the account parameter is not needed, you can refer to this example: [ipfs.ts](https://github.com/NuLink-network/nulink-sdk/blob/crosschain/src/core/utils/external-storage/implement/ipfs.ts)

<br/>

### With these preparations done, we can now proceed to the code for the pre process

    Here's the story: We have two characters in our story. One is named Alice, who uploads the data. The other is Bob, who wants to use the data uploaded by Alice. So, Bob requests Alice's uploaded data in our network. Once Alice sees Bob's request in our system, she has the option to either reject the request, in which case Bob cannot access the data, or approve Bob's request. If Alice approves the request, she can send an on-chain approval transaction, and upon successful approval, Bob can download the file to view or use it.

### <a id="PreCreateWallet">Create Wallet for Alice</a>

First, In order to use the pre process, we need to first create an account.

```javascript

//First, we import all the required libraries.
import {
  isBlank,
  restoreWalletDataByMnemonic,
  getPolicyGasFee,
  type DataInfo,
  DataCategory,
  uploadDataByCreatePolicy,
  getUploadedData,
  createAccountIfNotExist,
  getOtherShareData,
  getDataDetails,
  applyForDataUsagePermission,
  getDataPendingApprovalAsPublisher,
  refusalApplicationForUseData,
  getPolicyTokenCost,
  approvalApplicationForUseData,
  getApprovedDataAsPublisher,
  getApprovedDataAsUser,
  getDataContentByDataIdAsUser,
  getPublishedPoliciesInfo,
  uploadDataBySelectPolicy,
  getDataByStatus,
  getMnemonic,
  getDefaultAccountPrivateKey,
  logoutWallet,
  GasInfo
} from "@nulink_network/nulink-sdk";

import assert from "assert-ts";

import { BigNumber, ethers } from "ethers";
import { nanoid } from "nanoid";
import Web3 from "web3";

// Declaring and intializing the mnemonic and password variables.
const password: string = "1";

//first We create Alice's wallet and account by password
const nuLinkHDWallet1: NuLinkHDWallet = await createWallet(password);

assert(nuLinkHDWallet1);

// after we created the wallet, we can loadWallet by password
const nuLinkHDWallet2: NuLinkHDWallet | null = await loadWallet(password);
assert(nuLinkHDWallet2);

const nuLinkHDWallet = nuLinkHDWallet2 as NuLinkHDWallet;

assert(nuLinkHDWallet1 === nuLinkHDWallet);

//also, We can verify whether the user's password is correct
const correct: boolean = await verifyPassword(password);

assert(correct);

// We can also determine if the user has created an account locally
const hasAnAccountInLocal: boolean = await existDefaultAccount();
assert(hasAnAccountInLocal);

// we can get the account by user password that we have created
const accountAlice: Account = (await getWalletDefaultAccount(password)) as Account;
assert(accountAlice);
```

### <a id="UploadData">Alice upload data/files for encrypted</a>

Next, we will upload data using the account we just created, which we'll refer to as "Alice."

```javascript

// account Alice: as the publisher of the file (file uploader).

// Note: We only support one account currently.

//Now we can encrypt and upload a file for others to apply for download

//1. read a file
const plainText = 'file-content....';
const enc = new TextEncoder(); // always utf-8
const historyContent: Uint8Array = enc.encode(plainText);

//1.Alice upload file
const dataList: DataInfo[] = [
  {
    //label: A unique identifier for the file (similar to the file name) that is displayed to the user who needs to apply for the file
    label: `history-${nanoid()}.pdf`,
    dataArrayBuffer: historyContent.buffer,
  },
];

//2. Alice encrypt and update a file to the ipfs network
await uploadDataByCreatePolicy(accountAlice, DataCategory.History, dataList);

//3. We can get the file just uploaded
const resultList = (await getUploadedData(accountAlice, undefined, 1, 1000)) as object;

console.log("resultList: ", resultList);
console.log('resultList["total"]>0 ', resultList["total"] > 0);
assert(resultList && resultList["total"] > 0);

let fileIndex = -1;
for (let index = 0; index < resultList["list"].length; index++) {
  const element = resultList["list"][index];
  if (element["file_name"] === dataList[0]["name"]) {
    fileIndex = index;
    break;
  }
}
assert(fileIndex >= 0);
const uploadDataInfo = resultList["list"][fileIndex];

assert(uploadDataInfo["owner_id"] === accountAlice.id);
```

### <a id="UseData"> Bob requests to use the data/files uploaded by Alice</a>

Then: Bob, far away on the other side of the ocean, wants to use Alice's uploaded data.

1.create wallet for Bob

```javascript
// Bob, far away on the other side of the ocean, wants to use Alice's uploaded data
//  account Bob: as the user of the data/file ( data/file requester)

//don't forget import libirary ....

//Bob find the  data/file on Internet
const password: string = "1";

//Create Wallet for Bob
//first We create Bob's wallet and account by password
const nuLinkHDWallet: NuLinkHDWallet = await createWallet(password);

assert(nuLinkHDWallet);

  // we can get the account by user password that we have created
  const _accountBob: Account = (await getWalletDefaultAccount(password)) as Account;
  assert(_accountBob);
```

2.Bob views the details of the data that Alice just uploaded by checking the online information of other users' uploaded data.

```javascript
//Bob finds the file Bob has just uploaded
const dataDataResultList = (await getOtherShareData(_accountBob,undefined, false, undefined,
undefined, undefined, 1, 1000
)) as object;

assert(dataDataResultList && dataDataResultList["total"] > 0);

let dataIndex2 = -1;
for (let index = 0; index < dataDataResultList["list"].length; index++) {
  const element = dataDataResultList["list"][index];
  if (element["file_name"] === dataList[0]["name"]) {
    dataIndex2 = index;
    break;
  }
}
assert(dataIndex2 >= 0);

const findDataInfo = dataDataResultList["list"][dataIndex2];
assert(findDataInfo["owner_id"] === accountAlice.id);

const applyDataId = findDataInfo["file_id"];

//get data details
const dataDetails = (await getDataDetails(applyDataId, _accountBob.id)) as object;

//assert(dataDetails["creator_id"] === accountAlice.id);
assert(dataDetails["file_id"] === applyDataId);
assert(parseInt(dataDetails["status"]) === 0); //Is not to apply for
```

3.Bob is particularly interested in the data uploaded by Alice. So, Bob requests to use the data that Alice has just uploaded.

```javascript
//Bob requests permission to use the data for 7 days
try {
  await applyForDataUsagePermission(applyDataId, _accountBob, 7);
} catch (e) {
  console.log("bob apply data failed", e);
  assert(false);
}
```

4.Alice reviews the usage requests from others for the data she uploaded.

At first, Alice rejected Bob's request to use the data.

```javascript
//Alice receives Bob's data usage request

// Alice reviews the usage requests from others for the data she uploaded.
const dataNeedToApprovedResultList = await getDataPendingApprovalAsPublisher(accountAlice, 1, 1000);

let fileIndex3 = -1;
for (
  let index = 0;
  index < dataNeedToApprovedResultList["list"].length;
  index++
) {
  const element = dataNeedToApprovedResultList["list"][index];
  if (element["file_id"] === applyDataId) {
    fileIndex3 = index;
    break;
  }
}
assert(fileIndex3 >= 0);

assert(dataNeedToApprovedResultList && dataNeedToApprovedResultList["total"] > 0);
const needToApprovedDataInfo =
  dataNeedToApprovedResultList["list"][fileIndex3];
assert(needToApprovedDataInfo["file_owner_id"] === accountAlice.id);

//Alice rejected the file usage request
await refusalApplicationForUseData(accountAlice, needToApprovedDataInfo["apply_id"]);
```

5.Bob finds this file to be very useful, so he makes a second request.

```javascript
//Bob apply file for usage again. The application period is three days, less than the previous seven days
try {
  await applyForDataUsagePermission(applyDataId, _accountBob, 3);
} catch (e) {
  console.log("bob reapply file failed", e);
  assert(false);
}
```

### <a id="ApproveData">Alice approves Bob's request to use the file</a>
1.Alice is moved by Bob's persistence and after much consideration, she finally agrees to Bob's usage request.Since we need to send approval transactions to the current blockchain network, we first need to assess the gas fees as well as the service fees for requesting others' usage.

```javascript
//Alice receives Bob's file usage request again
const dataNeedToApprovedResultList2 = await getDataPendingApprovalAsPublisher(accountAlice, 1, 1000);

assert(
  dataNeedToApprovedResultList2 &&
    dataNeedToApprovedResultList2["total"] > 0
);

let dataIndex4 = -1;
for (
  let index = 0;
  index < dataNeedToApprovedResultList2["list"].length;
  index++
) {
  const element = dataNeedToApprovedResultList2["list"][index];
  if (element["file_id"] === applyDataId) {
    dataIndex4 = index;
    break;
  }
}
assert(dataIndex4 >= 0);

const needToApprovedDataInfo2 = dataNeedToApprovedResultList2["list"][dataIndex4];
assert(needToApprovedDataInfo2["file_owner_id"] === accountAlice.id);

//At this point Alice approves Bob's file usage request, Due to on-chain approval of Bob's request, we first evaluate gas and service fees

//1. Alice calc server fee (wei): 
//    For the main chain TBSC/BSC, the token is TNLK/NLK. 
//    For the side chains, they use the native currency of the respective chain (e.g., Mumbai uses TMATIC/MATIC, OKX X1 Chain uses TOKB/OKB).
const startDate: Date = new Date();
const startMs: number = Date.parse(startDate.toString());
const endMs: number =
  startMs + (needToApprovedDataInfo2["days"] as number) * 24 * 60 * 60 * 1000;
const endDate: Date = new Date(endMs); //  start_at is seconds, but Date needs milliseconds

const serverFeeNLKInWei: BigNumber = await getPolicyTokenCost(accountAlice, startDate, endDate, 2);

const serverValue = Web3.utils.fromWei(serverFeeNLKInWei.toString(), "ether");
console.log("server nlk fee  ether is:", serverValue);

//2. Alice calc gas fee (wei): the chain of bsc test token
const gasInfo: GasInfo = await getPolicyGasFee(
  _accountBob.id,
  needToApprovedDataInfo2["apply_id"],
  2,
  1,
  startMs/1000,
  endMs/1000,
  BigNumber.from(serverFeeNLKInWei)
);

//First, let's record the list of requests from other individuals that Alice has already approved, for future reference.
  const aliceApprovedfilesListLast = await getApprovedDataAsPublisher(
    accountAlice,
    1,
    1000
  );

//Note: Please make sure that the account has sufficient tnlk and bsc testnet tokens before this, otherwise the approval will fail
//Alice approves Bob's application for file usage. Whenever Alice approves a file request, an on-chain policy is created
await approvalApplicationForUseData(
  accountAlice,
  _accountBob.id,
  needToApprovedDataInfo2["apply_id"],
  2,
  1,
  startDate,
  endDate,
  "", //remark
  "", //porterUri
  gasInfo.gasFee
);
```

2.<space>As it is an on-chain transaction, there might be some delay. At this point, we need to wait for the on-chain transaction to be successfully confirmed by web3 before Alice can view her latest list of approved documents.

```javascript

let aliceApprovedDataList: any = null;
  do {
    await sleep(10000); //10 seconds
    //Alice, as the publisher of the file, obtains the list of files that she has successfully approved
    aliceApprovedDataList = await getApprovedDataAsPublisher(
      accountAlice,
      1,
      1000
    );
    /*return data format: {
      list: [
        { apply_id, file_id:, proposer, proposer_id, file_owner:, file_owner_id:, policy_id, hrac, start_at:, end_at, created_at }
        ...
      ],
      total: 300,
    }
  */
  } while (
    !aliceApprovedDataList ||
    aliceApprovedDataList["total"] <= aliceApprovedfilesListLast["total"]
  );

  assert(aliceApprovedDataList && aliceApprovedDataList["total"] > 0);
```

### <a id="BobGetData">Bob checks his list of requested files, and he can use the data now</a>
1.<space>At this point, Bob checks his list of requested files and discovers that Alice has approved his request to use the file.
So, Bob obtains the details of the document for future reference and downloading.

```javascript

//Record this policy ID and account Bob for future use.
let policyId;
let accountBob;
const dataIndex2s: number[] = [] //Array(numReqData).fill(-1);
  for (let index = 0; index < aliceApprovedDataList['list'].length; index++) {
    const element = aliceApprovedDataList['list'][index]
    if (element['file_id'] === applyDataId) {
      dataIndex2s.push(index)
      assert(element['file_owner_id'] === accountAlice.id)
      const _policyId = element['policy_id']
      policyId = _policyId;
      //console.log(`index_${index} data/file policy Id: ${_policyId}`)
      const accountBobId = element['proposer_id']
      const _accountBob = bobAccountId2AccountMap[accountBobId]
      accountBob = _accountBob;
      //Bob finds out that his application has been approved by Alice. Bob now has permission to view the contents of the file
      const bobBeApprovedDataList = await pre.getApprovedDataAsUser(_accountBob, 1, 1000)
      /*return data format: {
                              list: [
                                { apply_id, file_id:, proposer, proposer_id, file_owner:, file_owner_id:, policy_id, hrac,
                                  start_at:, end_at, created_at }
                                ...
                              ],
                              total: 300,
                            }
      */

      assert(bobBeApprovedDataList && bobBeApprovedDataList['total'] > 0)

      let dataIndex6 = -1
      for (let index = 0; index < bobBeApprovedDataList['list'].length; index++) {
        const element = bobBeApprovedDataList['list'][index]
        if (element['file_id'] === applyDataId) {
          dataIndex6 = index
          break
        }
      }
      assert(dataIndex6 >= 0)

      const bobBeApprovedDataInfo = bobBeApprovedDataList['list'][dataIndex6]
      assert(bobBeApprovedDataInfo['file_owner_id'] === accountAlice.id)
      const policyId2 = bobBeApprovedDataInfo['policy_id']
      assert(policyId2 === _policyId)

```

2.<space>At this point, Bob downloads and views the data.

```javascript
      //Finally, Bob gets the contents of the data/file
      const arrayBuffer: ArrayBuffer = await pre.getDataContentByDataIdAsUser(
        _accountBob,
        bobBeApprovedDataInfo['file_id']
      )
      const dataContent: string = Buffer.from(arrayBuffer).toString()
      console.log('dataContent: ', dataContent)
      console.log('plainText: ', plainText)
      assert(dataContent === plainText)

      //finish
    }
  }

  assert(dataIndex2s.length >= 0 && dataIndex2s.length > 0)
  //finish
```

### <a id="AliceMore">Alice obtain the on-chain policy information published by herself</a>
Also, Whenever Alice approves a file request, an on-chain policy is created.
Alice can also obtain the on-chain policy information published by herself

```javascript

// Whenever Alice approves a file request, an on-chain policy is created
// Alice can also obtain the on-chain policy information published by herself
const dataPolicys = await getPublishedPoliciesInfo(accountAlice, 1, 1000);

assert(!isBlank(dataPolicys));
```

### <a id="AliceUploadDataBySelectPolicy">Alice upload file by select Published Policy</a>
1.Alice also can encrypt and update a file to the ipfs network by select an existing on-chain policy

```javascript
//Alice also can encrypt and update a file to the ipfs network by select an existing on-chain policy
const plainText2 = "This is a philosophy book content";
const historyContent2: Uint8Array = enc.encode(plainText2);

//1.upload file
const dataList2: DataInfo[] = [
  {
    label: `philosophy-${nanoid()}.pdf`,
    dataArrayBuffer: historyContent2.buffer,
  },
];

//Files/Data uploaded by using published policies do not need approval. Bob can use the files directly, so there is no approval record
const fileIds = await uploadDataBySelectPolicy(
  accountAlice,
  DataCategory.Philosophy,
  dataList2,
  policyId
);
```

### <a id="BobGetDataNoNeedApproveByAlice">Bob get data no need approve by Alice's published policys</a>
2.Bob can directly download Alice's associated policy upload file without waiting for Alice's approval, because the associated policy has already been created and does not need repeated approval.

```javascript
//Bob can directly download Alice's associated policy upload file without waiting for Alice's approval,
//because the associated policy has already been created and does not need repeated approval. Note: This publish policy value is available for Bob
//Bob get new upload file content
const arrayBuffer2: ArrayBuffer = await getDataContentByDataIdAsUser(
  _accountBob,
  fileIds[0]
);
const dataContent2: string = Buffer.from(arrayBuffer2).toString();
console.log("dataContent2: ", dataContent2);
console.log("plainText2: ", plainText2);
assert(dataContent2 === plainText2);

//you can get all status files for mine apply: The files I applied for
//status 0: all status, include:  applying, approved, rejected
const data = (await getDataByStatus(
  undefined,
  _accountBob.id,
  undefined,
  undefined,
  0,
  1,
  1000
)) as object;

assert(data && !isBlank(data) && data["total"] > 0);
```

### <a id="restoreWalletByMnemonic">Restore wallet by mnemonic</a>
For wallet more info, you can also restore wallet by mnemonic

```javascript
// we also can restore wallet by mnemonic

//get mnemonic from current wallet
const mnemonic: string = (await getMnemonic(password)) as string;

//You can also use the mnemonic word exported by metamask to restore the nulink wallet account
const newpassword = "111";
// restore an wallet to Browser localstorage/indexdb  by mnemonic, and we can set an new password when we restore an wallet
const nuLinkHDWalletRestore: NuLinkHDWallet =
  await restoreWalletDataByMnemonic(newpassword, mnemonic);
assert(nuLinkHDWallet != nuLinkHDWalletRestore);

//You can also export the private key of the nulink wallet account through the user password to import it into the metamask wallet
let privatekeyString = await getDefaultAccountPrivateKey(newpassword);
assert(privatekeyString != null);
privatekeyString = privatekeyString as string;

//When you are done using it, you can clear the browser's wallet cache data, and use the mnemonic to re-import it the next time you use it
await logoutWallet();
```

## API docs

<!--[API](./docs/modules.md) -->

[API Details](https://github.com/NuLink-network/nulink-sdk/tree/crosschain/docs/modules.md)

## More examples

[nulink-sdk-demo](https://github.com/NuLink-network/nulink-sdk-demo)
