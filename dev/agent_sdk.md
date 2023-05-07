# nulink-agent-sdk
The SDK for third-party integration with nulink-web-agent project.

## How to Use


### Install
```bash
npm i @nulink_network/nulink-web-agent-access-sdk
```
or
```bash
yarn add @nulink_network/nulink-web-agent-access-sdk
```

### Usage
#### Api
All APIs take a callback function as a parameter and execute the callBackFunc after the corresponding method is successfully executed.

The callback function type that takes an optional parameter responseData and returns a Promise object.
When the API call returns, the callback function is called with the responseData parameter, which is the data returned from the API call. The callback function can then process the data and handle any errors that occurred during the API call.
- connect


```connect``` is used for handling login functionality for nulink web agent. It opens a new window for the user to complete the login process, and then executes the callBackFunc with the login data when the login is successful.

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
```connect``` response data
```
loginResponseData : {
    accountAddress: string
    accountId: string
    action: 'login'
    result: string
    redirectUrl: string
}
```

- upload

```upload```used for uploading files and executing a callback function after the upload is successful
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
```upload``` response data

```
uploadResponseData : {
    accountAddress: string
    accountId: string
    action: 'upload'
    subAction?: string
    result: string
    redirectUrl: string
}
```
- apply


```apply``` The apply function is used for applying for filestakes, takes two parameters: applyInfo, which is an object containing information about the file to be applied for, and callBackFunc, which is the callback function to be executed after the application is successful.

```typescript
import { upload } from "@nulink_network/nulink-web-agent-access-sdk"

const applyForFile = async (values) => {
    const applyInfo: ApplyInfo = {
    fileCreatorAddress: detailItem.creator_address,
    fileId: detailItem.file_id,
    fileName: detailItem.file_name,
    usageDays: values.usageDays,
  };
  await apply(applyInfo, async () => {
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
```apply``` response data
```
applyResponseData : {
    accountAddress: string
    accountId: string
    action: 'apply'
    subAction?: string
    owner: string
    user: string
    result: string
    redirectUrl: string
}
```

- approve

  ```approve```is used for approving files, takes six parameters: applyId, applyUserId, applyUserAddress, days, remark, and callBackFunc.

```typescript
const approveSubmit = async () => {
    const { applyId, userAccountId } =
      useWalletParams as UseWalletPayRequestOptions;
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
```approve``` response data
```
approveResponseData : {
    accountAddress: string
    accountId: string
    action: string
    subAction?: string
    from: string
    to: string
    applyId: string
    result: string
    redirectUrl: string
}
```
- download

The fileDownload API provides the function of downloading files.

takes four parameters:
- fileId (a string): The ID of the file to be downloaded.
- fileName (a string): The name of the file to be downloaded.
- applyUserAddress (a string): The address of the user who has applied to download the file.
- callBackFunc (a function): A callback function that will be called with the response data from the server.

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
```download``` response data
```
decryptionResponseData : {
    accountAddress: string
    accountId: string
    fileName: string
    action: 'decrypted'
    subAction?: string
    result: string
    redirectUrl: string
    url?: string
}
```

## More examples

[nulink-web-agent-integration-demo](https://github.com/NuLink-network/nulink-web-agent-integration-demo.git) 