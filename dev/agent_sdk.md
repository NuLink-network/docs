# NuLink Agent SDK
The SDK for third-party integration with [NuLink Agent](../product/nulink_agent.md).

These APIs allow you to access NuLink Agent programmatically and perform various actions, such as connect, upload, apply, approve and download.


## How to Use

### Getting Started

The default address in the Nulink Web Agent Access SDK:

* NuLink Agent: https://agent.testnet.nulink.org, and the default 
* Backend service address: https://agent-integration-demo.nulink.org/bk. 

If you need to change these two addresses, you will need to write the following configurations in the .env file of your project: REACT_APP_NULINK_AGENT_ADDRESS for the web agent address and REACT_APP_NULINK_BACKEND_ADDRESS for the backend service address.

```
// modify .env in your project
// the web agent address
REACT_APP_NULINK_AGENT_ADDRESS=xxxxxx
// the agent bcakend service address
REACT_APP_NULINK_BACKEND_ADDRESS=xxxxxx
```

### Install
```bash
npm i @nulink_network/nulink-web-agent-access-sdk
```
or
```bash
yarn add @nulink_network/nulink-web-agent-access-sdk
```


## Usage

All APIs take a callback function as a parameter and execute the callBackFunc after the corresponding method is successfully executed.

The callback function type that takes an optional parameter responseData and returns a Promise object.
When the API call returns, the callback function is called with the responseData parameter, which is the data returned from the API call. The callback function can then process the data and handle any errors that occurred during the API call.

**CallBackFunc**
```typescript
type CallBackFunc =  ( responseData?:any ) => Promise<any>;
```

## Methods

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

### upload
```typescript
upload(callBackFunc:CallBackFunc)
```
```upload```used for uploading files and executing a callback function after the upload is successful

#### Parameters
- Promise : CallBackFunc - A callback function that will be called with the response data from the server.

#### Returns
```
 {
    accountAddress: string - the address of the logged-in user
    accountId: string - the ID of the logged-in user
    action: 'upload'
    subAction?: string
    result: string
    redirectUrl: string
}
```

#### Example

```typescript
import { upload } from "@nulink_network/nulink-web-agent-access-sdk"

const _uploadAction = async () => {
    await upload(async (data) => {
      if (responseData) {
        // Do something with the responseData
        console.log(responseData);
      } else {
        // Handle the error case
        console.error('Failed to upload');
      }
    })
}
```

### apply

```typescript
apply(fileCreatorAddress:string, fileId:string, fileName:string, usageDays: string, callBackFunc:CallBackFunc)
```

```apply``` The apply function is used for applying for files, takes four parameters: fileCreatorAddress,fileId,fileName,usageDays and callBackFunc, which is the callback function to be executed after the application is successful.

#### Parameters
- fileCreatorAddress : string - The file creator Address
- fileId : string - The file id
- fileName : string - The file name
- usageDays : string - The number of days applied
- Promise : CallBackFunc - A callback function that will be called with the response data from the server.

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
import { upload } from "@nulink_network/nulink-web-agent-access-sdk"

const applyForFile = async () => {
  await apply(fileCreatorAddress,fileId, fileName, usageDays, async () => {
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
approve(applyId:string,
         applyUserId:string,
         applyUserAddress:string,
         days:string,
         remark:string,
         callBackFunc:CallBackFunc)
```

```approve```is used for approving files, takes six parameters: applyId, applyUserId, applyUserAddress, days, remark, and callBackFunc.
#### Parameters
- applyId : string - the application ID
- applyUserId : string - the application user id
- applyUserAddress : string - the application user address
- days : string - the application days
- remark : string - the remark
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
const approveSubmit = async () => {
    await approve(applyId, userAccountId, currentRecord.proposer_address, currentRecord.days, currentRecord.remark, async () => {
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
download(fileId:string, fileName:string, applyUserAddress:string, callBackFunc:CallBackFunc)
```

The fileDownload API provides the function of downloading files.

#### Parameters

- fileId : string - The ID of the file to be downloaded.
- fileName : string - The name of the file to be downloaded.
- applyUserAddress : string - The address of the user who has applied to download the file.
- Promise : CallBackFunc - A callback function that will be called with the response data from the server.

#### Returns
```
{
  accountAddress: string - the address of the logged-in user
  accountId: string - the Id of the logged-in user
  fileName: string - the request file name
  action: 'decrypted'
  subAction?: string
  result: string
  redirectUrl: string
  url?: string - the file ipfs address
}
```

#### Example

```typescript
const fileDownload = async () => {
    await download(detailItem.file_id,detailItem.file_name, detailItem.file_owner_address, fileDownloadCallBack);
  };

  const fileDownloadCallBack = async (data) => {
    try {
      if (!!data && data.url) {
        const arraybuffer = await getData(decodeURIComponent(data.url))
        const blob = new Blob([arraybuffer], { type: "arraybuffer" });
        let url = window.URL.createObjectURL(blob);
        const link = document.createElement("a");
        link.style.display = "none";
        link.href = url;
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
getFileDetail(accountId:string, include:boolean, desc:boolean = false, pageNum:number, pageSize:number)
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
        file_id: string - File ID
        file_name: string - File name
        category: string - File category/type
        format: string - File format
        suffix: string - File suffix
        address: string - File address
        thumbnail: string - File thumbnail
        owner: string - File owner
        owner_id: string - File owner's account ID
        owner_avatar: string - File owner's avatar
        created_at: number - File upload timestamp
    }]
}
```

#### Example
```typescript
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
{
    file_id: string - File ID
    file_name: string - File name
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
}
```

#### Example
```typescript
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
{
    file_id: string - File ID
    file_name: string - File name
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
}
```

#### Example
```typescript
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
{
    file_id: string - File ID
    file_name: string - File name
    thumbnail: string - File thumbnail
    apply_id: number - Application record ID
    proposer: string - Applicant name
    proposer_id: string - Applicant account ID
    proposer_address: string - Applicant's Ethereum address
    file_owner: string - File owner name
    file_owner_id: string - File owner account ID
    file_owner_address: string - File owner's Ethereum address
    status: number - Application status, 1: applying, 2: approved, 3: rejected
    remark: string - Approval comment or remark
    start_at: number - Application start timestamp
    end_at: number - Application end timestamp
    created_at: number - Application timestamp
    policy_id: number - Policy ID
    policy_label_id: string - Policy label ID
    hrac: string - Policy HRAC code
}
```

#### Example
```typescript
const _getIncomingApplyFiles = async () => {
    let result = await getIncomingApplyFiles(
        proposerId, status, pageNum, pageSize
    );
    dealWithResultList(result);
};

```

## More examples

[nulink-web-agent-integration-demo](https://github.com/NuLink-network/nulink-web-agent-integration-demo.git) 