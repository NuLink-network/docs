


# NuLink Agent API

All APIs take a callback function as a parameter and execute the callBackFunc after the corresponding method is successfully executed.

The callback function type that takes an optional parameter responseData and returns a Promise object.
When the API call returns, the callback function is called with the responseData parameter, which is the data returned from the API call. The callback function can then process the data and handle any errors that occurred during the API call.

**CallBackFunc**
```typescript
type CallBackFunc =  ( responseData?:any ) => Promise<any>;
```

## Methods

### Workflow API
- [connect](#connect)
- [uploadData](#uploaddata)
- [uploadDataBatch](#uploaddatabatch)
- [uploadFile](#uploadfile)
- [uploadFileBatch](#uploadfilebatch)
- [apply](#apply)
- [approve](#approve)
- [download](#download)
### Platform data API
- [getFileList](#getfilelist)
- [getFileDetail](#getfiledetail)
- [getSendApplyFiles](#getsendapplyfiles)
- [getIncomingApplyFiles](#getincomingapplyfiles)
- [getUrsulaNumber](#getursulanumber)
- [getNetWorkChainId](#getnetworkchainid)
- [setNetWorkChainId](#setnetworkchainid)
- [sendCustomTransaction](#sendcustomtransaction)

### connect

  ```typescript
  connect(callBackFunc:CallBackFunc)
  ```

```connect``` is used for handling login functionality for nulink web agent. It opens a new window for the user to complete the login process, and then executes the callBackFunc with the login data when the login is successful.

#### Parameters
- Promise : CallBackFunc - A callback function that will be called with the response data from the server.

#### Returns

```
{
    accountAddress: string - the address of the logged-in user
    accountId: string - the ID of the logged-in user
    action: 'login' - the action type
    result: string
    redirectUrl: string
}
```

#### Example

```typescript
import { connect } from "@nulink_network/nulink-web-agent-access-sdk"

const gotoConnect = async () => {
    await connect(loginSuccessHandler)
}

const loginSuccessHandler: CallBackFunc = async (responseData) => {
  if (responseData) {
    // Do something with the responseData
    console.log(responseData);
  } else {
    // Handle the error case
    console.error('Failed to login in');
  }
}
```

### uploadData
```typescript
uploadData(_uploadData: UploadData, callBackFunc:CallBackFunc)
```

```uploadData```used for uploading data and executing a callback function after the upload is successful

``` 
type UploadData = {
    dataLabel : string,
    fileBinaryArrayBuffer: Blob
}
```

#### Parameters
- _uploadData: UploadData - The type UploadData is defined as an object with properties dataLabel of type string and fileBinaryArrayBuffer of type Blob
- Promise : CallBackFunc - A callback function that will be called with the response data from the server

#### Returns
```
 {
    accountAddress: string
    accountId: string
    action: 'upload'
    subAction?: string
    dataInfo?: [{dataHash: string, dataLabel : string}]
    result: 'success' | 'failed'
    redirectUrl: string
    errorMsg?: any
}
```

#### Example

```typescript
import { uploadData } from "@nulink_network/nulink-web-agent-access-sdk"

const _uploadAction = async () => {
    await uploadData({ dataLabel : dataLabel, fileBinaryArrayBuffer: blob }, async (responseData) => {
      if (responseData) {
        // Do something with the responseData
        console.log(responseData.dataInfo);
      } else {
        // Handle the error case
        console.error('Failed to upload');
      }
    })
}
```

### uploadDataBatch
```typescript
uploadDataBatch(dataList: UploadData[], callBackFunc:CallBackFunc)
```

```uploadDataBatch``` allows batch uploading of data and executes a callback function after the upload is successful

``` 
type UploadData = {
    dataLabel : string,
    fileBinaryArrayBuffer: Blob
}
```

#### Parameters
- dataList: UploadData[] - an array of UploadData objects
- Promise : CallBackFunc - A callback function that will be called with the response data from the server

#### Returns
```
 {
    accountAddress: string
    accountId: string
    action: 'upload'
    subAction?: string
    dataInfo?: [{dataHash: string, dataLabel : string}]
    result: 'success' | 'failed'
    redirectUrl: string
    errorMsg?: any
}
```

#### Example

```typescript
import { uploadDataBatch } from "@nulink_network/nulink-web-agent-access-sdk"

const _uploadAction = async () => {
    await uploadDataBatch(dataList, async (responseData) => {
      if (responseData) {
        // Do something with the responseData
        console.log(responseData.dataInfo);
      } else {
        // Handle the error case
        console.error('Failed to upload');
      }
    })
}
```

### uploadFile
```typescript
uploadFile(file: File, callBackFunc:CallBackFunc)
```

```uploadFile``` uploading file and executing a callback function after the upload is successful


#### Parameters
- file : File - the file to be uploaded, of type File
- Promise : CallBackFunc - A callback function that will be called with the response data from the server

#### Returns
```
 {
    accountAddress: string
    accountId: string
    action: 'upload'
    subAction?: string
    dataInfo?: [{dataHash: string, dataLabel : string}]
    result: 'success' | 'failed'
    redirectUrl: string
    errorMsg?: any
}
```

#### Example

```typescript
import { uploadFile } from "@nulink_network/nulink-web-agent-access-sdk"

const _uploadAction = async () => {
    await uploadFile( file, async (responseData) => {
      if (responseData) {
        // Do something with the responseData
        console.log(responseData.dataInfo);
      } else {
        // Handle the error case
        console.error('Failed to upload');
      }
    })
}
```

### uploadFileBatch
```typescript
uploadFileBatch(files: File[], callBackFunc:CallBackFunc)
```

```uploadFileBatch``` allows batch uploading of file and executes a callback function after the upload is successful

#### Parameters
- files: File[] - the files to be uploaded, an array of File
- Promise : CallBackFunc - A callback function that will be called with the response data from the server

#### Returns
```
 {
    accountAddress: string
    accountId: string
    action: 'upload'
    subAction?: string
    dataInfo?: [{dataHash: string, dataLabel : string}]
    result: 'success' | 'failed'
    redirectUrl: string
    errorMsg?: any
}
```

#### Example

```typescript
import { uploadFileBatch } from "@nulink_network/nulink-web-agent-access-sdk"

const _uploadAction = async () => {
    await uploadFileBatch( files, async (responseData) => {
      if (responseData) {
        // Do something with the responseData
        console.log(responseData.dataInfo);
      } else {
        // Handle the error case
        console.error('Failed to upload');
      }
    })
}
```

### apply

```typescript
apply(dataName: string,
      dataId: string,
      dataCreatorAddress: string,
      dataStorageUrl: string,
      dataHash: string,
      zkProof: string,
      usageDays: number,
      callBackFunc:CallBackFunc)
```

```apply``` The apply function is used for applying for files, takes eight parameters: dataCreatorAddress,dataId,dataName,dataStorageUrl,
dataHash,zkProof,usageDays and callBackFunc, which is the callback function to be executed after the application is successful.

#### Parameters
- dataName : string - The data name
- dataId : string - The data id
- dataCreatorAddress : string - The data creator Address
- dataUrl : string - The data storage url
- dataHash : string - The data hash
- zkProof : string - The data zkProof
- usageDays : number - The number of days applied
- Promise : CallBackFunc - A callback function that will be called with the response data from the server.

The parameters in the ``` apply ``` API can be obtained from the response of the ``` getFileList``` ``` getFileDetail```

#### Returns
```
{
    accountAddress: string - the address of the logged-in user
    accountId: string - the ID of the logged-in user
    action: 'apply'
    subAction?: string
    owner: string - the file owner's address
    user: string - the file requester's address
    result: string
    redirectUrl: string
}
```

#### Example

```typescript
import { apply } from "@nulink_network/nulink-web-agent-access-sdk"

const applyForFile = async () => {
  await apply(_dataName, _dataId, _dataCreatorAddress, _dataUrl, _dataHash, _zkProof, _usageDays, async () => {
    if (responseData) {
      // Do something with the responseData
      console.log(responseData);
    } else {
      // Handle the error case
      console.error('Failed to upload');
    }
  });
};
```

### approve
```typescript
approve(applyId : string,
        applyUserAddress : string,
        applyUserId : string,
        dataName : string,
        dataHash : string,
        dataStorageUrl : string,
        days : string,
        backupNodeNum : number,
        callBackFunc : CallBackFunc)
```

```approve```is used for approving files, takes parameters: applyId, applyUserAddress, applyUserId, dataName, dataHash, dataUrl, days, backupNodeNum and callBackFunc.
#### Parameters
- applyId : string - the application ID
- applyUserId : string - the application user id
- applyUserAddress : string - the application user address
- dataName : string - The data name
- dataUrl : string - The data storage url
- dataHash : string - The data hash
- days : string - the application days
- backupNodeNum : number - number of nodes used for data backup, this number is the response of ``` getUrsulaNumber ``` API
- Promise : CallBackFunc - A callback function that will be called with the response data from the server.

#### Returns
```
{
    accountAddress: string - the address of the logged-in user
    accountId: string - the Id of the logged-in user
    action: string
    subAction?: string
    from: string - the file owner's address
    to: string - the file requester's address
    applyId: string - the apply id
    result: string
    redirectUrl: string
}
```

#### Example

```typescript
import { approve } from "@nulink_network/nulink-web-agent-access-sdk"

const approveSubmit = async () => {
    await approve(_applyId, _applyUserId, _applyUserAddress, _dataName, _dataUrl, _dataHash,  _days, _backupNodeNum, async () => {
      if (responseData) {
        // Do something with the responseData
        console.log(responseData);
      } else {
        // Handle the error case
        console.error('Failed to upload');
      }
    });
  };
```

### download

```typescript
download(dataId:string,
         dataName:string,
         dataHash: string,
         ownerAddress:string,
         zkProof: string,
         dataUrl: string,
         encryptedDataSize: string,
         callBackFunc:CallBackFunc)
```

The dataDownload API provides the function of downloading files.

#### Parameters

- dataId : string - The ID of the data to be downloaded
- dataName : string - The name of the data to be downloaded
- dataHash : string - The hash of the data to be downloaded
- ownerAddress : string - The owner of the data
- zkProof : string - The zk proof of the data
- dataUrl : string - The data storage url
- encryptedDataSize - The size of encrypted data
- Promise : CallBackFunc - A callback function that will be called with the response data from the server.

#### Returns
```
{
  accountAddress: string
    accountId: string
    fileName: string
    action: 'decrypted'
    subAction?: string
    result: 'success' | 'failed'
    redirectUrl: string
    arrayBuffer?: string - The ArrayBuffer of the raw data
    errorMsg?: any
}
```

#### Example

```typescript
import { download }  from "@nulink_network/nulink-web-agent-access-sdk"

const fileDownload = async () => {
    await download(
        detailItem.file_id,
        detailItem.file_name,
        detailItem.file_hash,
        detailItem.creator_address,
        detailItem.file_zk_proof,
        detailItem.file_url,
        detailItem.file_encrypted_size,
        fileDownloadCallBack,
    );
};

const fileDownloadCallBack = async (data) => {
    try {
        if (!!data && data.arrayBuffer) {
            const blob = new Blob([data.arrayBuffer], { type: 'arraybuffer' })
            const url = window.URL.createObjectURL(blob)
            const link = document.createElement("a");
            link.style.display = "none";
            link.href = url
            link.setAttribute("download", data.fileName);
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        }
    }catch (error){
        throw new Error("Decryption failed, Please try again")
    }
}
```

### getFileList

```typescript
getFileList(accountId:string, include:boolean, desc:boolean = false, pageNum:number, pageSize:number)
```
Get the list of files belonging to other users.

#### Parameters
- accountId : string - ID of the currently logged-in user
- include : boolean - If include=false, exclude the files belonging to the current account; otherwise, the files belonging to the current user will be placed at the beginning of the list.
- desc : boolean - Whether to sort in descending order by upload time
- pageNum : number - page number (starting from 1)
- pageSize : number - page size

#### Returns
```typescript
{
    total: number
    list: [{
        file_id: string - the file ID
        file_name: string - the file name
        file_hash: string - the file hash
        file_raw_size: string - the original file size
        file_zk_proof: string - the zero-knowledge proof of file
        file_encrypted_size: string - The size of the encrypted file
        category: string - the file category/type
        format: string - file format
        suffix: string - file suffix
        address: string - file address
        thumbnail: string - file thumbnail
        owner: string - file owner
        file_url: string - file storage url
        address: string - the file hash in backend
        owner_id: string - file owner's account ID
        owner_avatar: string - file owner's avatar
        created_at: number - file upload timestamp
    }]
}
```

#### Example
```typescript
import { getFileList }  from "@nulink_network/nulink-web-agent-access-sdk"

const pageChange = async () => {
    let result = await getFileList(
        accountId, include, desc, pageNum, pageSize
    );
    dealWithResultList(result);
  };

```

### getFileDetail

```typescript
getFileDetail(fileId:string, fileUserAccountId:string)
```
get file details

#### Parameters
- fileId : string - the file id
- fileUserAccountId : string - The file user's account ID, which refers to the current user's account ID.

#### Returns
```typescript
[{
    file_id: string - File ID
    file_name: string - File name
    file_hash: string - the file hash
    file_raw_size: string - the original file size
    file_zk_proof: string - the zero-knowledge proof of file
    file_encrypted_size: string - The size of the encrypted file
    thumbnail: string - File thumbnail
    creator: string - Owner of the file (policy creator)
    creator_id: string - Owner ID of the file (policy creator ID)
    creator_avatar: string - Owner avatar of the file (policy creator avatar)
    creator_address: string - Ethereum address of the file owner (policy creator's address)
    file_created_at: number - File upload timestamp
    apply_id: number - Application record ID
    proposer_address: string - Ethereum address of the file user (policy user's address)
    status: number - Application status, 0: not applied, 1: applying, 2: approved, 3: rejected
    apply_start_at: string - Application start timestamp (policy start timestamp)
    apply_end_at: string - Application end timestamp (policy end timestamp)
    apply_created_at: string - Submit application timestamp
    policy_id: number - Policy ID
    hrac: string - Policy HRAC
    consumer: string - Policy user (applicant, file user)
    consumer_id: string - Policy user ID
    gas: string - Policy gas
    tx_hash: string - Policy transaction hash
    policy_created_at: string - Policy creation timestamp
    file_ipfs_address: string - File IPFS address
    policy_encrypted_pk: string - Encrypted public key of the policy
    encrypted_treasure_map_ipfs_address: string - Policy treasure map address
    alice_verify_pk: string - File owner's Verify public key
}]
```

#### Example
```typescript
import { getFileDetail }  from "@nulink_network/nulink-web-agent-access-sdk"

const _getFileDetail = async () => {
    let result = await getFileDetail(
        fileId, fileUserAccountId
    );
    dealWithdETAILResult(result);
  };

```

### getSendApplyFiles

```typescript
getSendApplyFiles(proposerId:string, status:number, pageNum:number, pageSize:number)
```
Function to fetch send application files

#### Parameters
- proposerId: string - Applicant's account ID
- status: number - Application status 0:no distinction, 1: applying, 2: approved, 3: rejected, 4: in progress, 5: expired
- pageNum: number - the page number
- pageSize: number - the page size

#### Returns
```typescript
[{
    file_id: string - File ID
    file_name: string - File name
    file_hash: string - the file hash
    file_raw_size: string - the original file size
    file_zk_proof: string - the zero-knowledge proof of file
    file_encrypted_size: string - The size of the encrypted file
    thumbnail: string - File thumbnail
    apply_id: number - Application record ID
    proposer: string - Applicant name
    proposer_id: string - Applicant account ID
    proposer_address: string - Applicant's address
    file_owner: string - File owner name
    file_owner_id: string - File owner account ID
    file_owner_address: string - File owner's address
    status: number - Application status, 1: applying, 2: approved, 3: rejected
    remark: string - Approval comment or remark
    start_at: number - Application start timestamp
    end_at: number - Application end timestamp
    created_at: number - Application timestamp
    policy_id: number - Policy ID
    policy_label_id: string - Policy label ID
    hrac: string - Policy HRAC code
}]
```

#### Example
```typescript
import { getSendApplyFiles }  from "@nulink_network/nulink-web-agent-access-sdk"

const _getSendApplyFiles = async () => {
    let result = await getSendApplyFiles(
        proposerId, status, pageNum, pageSize
    );
    dealWithResultList(result);
};

```

### getIncomingApplyFiles

```typescript
getIncomingApplyFiles(fileOwnerId:string, status:number, pageNum:number, pageSize:number)
```
Function to fetch the received application files

#### Parameters
- fileOwnerId: string - File owner's account ID
- status: number - Application status 0:no distinction, 1: applying, 2: approved, 3: rejected, 4: in progress, 5: expired
- pageNum: number - the page number
- pageSize: number - the page size

#### Returns
```typescript
[{
    file_id: string - File ID
    file_name: string - File name
    file_hash: string - the file hash
    file_raw_size: string - the original file size
    file_zk_proof: string - the zero-knowledge proof of file
    file_encrypted_size: string - The size of the encrypted file
    thumbnail: string - File thumbnail
    apply_id: number - Application record ID
    proposer: string - Applicant name
    proposer_id: string - Applicant account ID
    proposer_address: string - Applicant's address
    file_owner: string - File owner name
    file_owner_id: string - File owner account ID
    file_owner_address: string - File owner's address
    status: number - Application status, 1: applying, 2: approved, 3: rejected
    remark: string - Approval comment or remark
    start_at: number - Application start timestamp
    end_at: number - Application end timestamp
    created_at: number - Application timestamp
    policy_id: number - Policy ID
    policy_label_id: string - Policy label ID
    hrac: string - Policy HRAC code
}]
```

#### Example
```typescript
import { getIncomingApplyFiles }  from "@nulink_network/nulink-web-agent-access-sdk"

const _getIncomingApplyFiles = async () => {
    let result = await getIncomingApplyFiles(
        proposerId, status, pageNum, pageSize
    );
    dealWithResultList(result);
};

```

### getUrsulaNumber

```typescript
getUrsulaNumber()
```
Function to fetch the backup nodes number of ursula

#### Parameters
    None

#### Returns
```typescript
    ursulaNumber : number 
```

#### Example
```typescript
import { getUrsulaNumber }  from "@nulink_network/nulink-web-agent-access-sdk"

let ursulaNum = await getUrsulaNumber()

```


### getNetWorkChainId

```typescript
getNetWorkChainId()
```
Function to get the network info

#### Parameters
  None

#### Returns
```typescript
    chinId: number - the network chain id
```

#### Example
```typescript
import { getNetWorkChainId }  from "@nulink_network/nulink-web-agent-access-sdk"

const _getNetWorkChainId = async () => {
    let chainId = await getNetWorkChainId();
    // do something
};

```

### setNetWorkChainId

```typescript
getNetWorkChainId(chainId : string )
```
Function to get the network info

#### Parameters
```typescript
    chainId : string - the network chain id which you will set
```

#### Returns
 None

#### Example
```typescript
import { setNetWorkChainId }  from "@nulink_network/nulink-web-agent-access-sdk"

const _setNetWorkChainId = async () => {
    await getNetWorkChainId(97);
    // do something
};

```
### sendCustomTransaction

```typescript
  sendCustomTransaction(callBackFunc:CallBackFunc, toAddress: string, rawTxData?: string, value?: string, gasPrice?: string)
```
send custom transaction by agent website

#### Parameters
- Promise: CallBackFunc - A callback function that will be called with the response data from the server.
- toAddress: string - The recevier of the transaction.
- rawTxData?: string - The call data of the transaction, can be empty for simple value transfers.
- value?: string - The value of the transaction in wei.
- gasPrice?: string - The gas price (wei) set by this transaction, if empty, it will use web3.eth.getGasPrice()

#### Returns
```typescript
{
  accountAddress: string - the address of the logged-in user
  accountId: string - the Id of the logged-in user
  toAddress: string - The receiving address
  rawTxData?: string - The call data of the transaction
  value?: string - The value of the transaction in wei
  gasPrice?: string - The gas price (wei) set by this transaction
  action: string - "transaction"
  subAction?: string
  result: string - 'success' or 'filed'
  transactionHash?: string - the transaction hash, if success
  errorMsg?: any - the error message
}
```

#### Example
```typescript
import {
  sendCustomTransaction
} from "@nulink_network/nulink-web-agent-access-sdk";

const sendTransaction = async () => {
  await sendCustomTransaction(sendTransactionCallBack, toAddress, null, value)
}

const sendTransactionCallBack = async (data) => {
  try {
    if ('success' == data.result){
        //do something
    } else {
        //do something
    }
  } catch (error) {
    throw new Error("Transaction failed, Please try again");
  }
};
```
