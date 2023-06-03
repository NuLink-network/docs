
# NuLink SDK Examples

## Usage

### Encrypt and Upload file

```javascript

// account Alice: as the publisher of the file (file uploader). 
//
import {
  AccountManager,
  NuLinkHDWallet,
  Account,
  createWallet,
  loadWallet,
  verifyPassword,
  existDefaultAccount,
  isBlank,
  restoreWalletDataByMnemonic,
  getPolicyGasFee,
  type FileInfo,
  getWalletDefaultAccount,
  FileCategory,
  uploadFilesByCreatePolicy,
  getUploadedFiles,
  createAccountIfNotExist,
  getOtherShareFiles,
  getFileDetails,
  applyForFilesUsagePermission,
  getFilesPendingApprovalAsPublisher,
  refusalApplicationForUseFiles,
  getPolicyTokenCost,
  approvalApplicationForUseFiles,
  getApprovedFilesAsPublisher,
  getApprovedFilesAsUser,
  getFileContentByFileIdAsUser,
  getPublishedPoliciesInfo,
  uploadFilesBySelectPolicy,
  getFilesByStatus,
  getMnemonic,
  getDefaultAccountPrivateKey,
  logoutWallet,
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

// Note: We only support one account currently.

//Now we can encrypt and upload a file for others to apply for download

//1. read a file
const plainText = 'file-content....';
const enc = new TextEncoder(); // always utf-8
const historyContent: Uint8Array = enc.encode(plainText);

//1.Alice upload file
const fileList: FileInfo[] = [
  {
    name: `history-${nanoid()}.pdf`,
    fileBinaryArrayBuffer: historyContent.buffer,
  },
];

//2. Alice encrypt and update a file to the ipfs network
await uploadFilesByCreatePolicy(accountAlice, FileCategory.History, fileList);

//3. We can get the file just uploaded
const resultList = (await getUploadedFiles(accountAlice, undefined, 1, 1000)) as object;

console.log("resultList: ", resultList);
console.log('resultList["total"]>0 ', resultList["total"] > 0);
assert(resultList && resultList["total"] > 0);

let fileIndex = -1;
for (let index = 0; index < resultList["list"].length; index++) {
  const element = resultList["list"][index];
  if (element["file_name"] === fileList[0]["name"]) {
    fileIndex = index;
    break;
  }
}
assert(fileIndex >= 0);
const uploadFileInfo = resultList["list"][fileIndex];

assert(uploadFileInfo["owner_id"] === accountAlice.id);
```


### Request and Grant the access


```javascript
// Bob, far away on the other side of the ocean, wants to use Alice's uploaded file
//  account Bob: as the user of the file (file requester)

//don' forget import libirary ....

//Bob find the file on Internet
const password: string = "1";

//first We create Bob's wallet and account by password
const nuLinkHDWallet: NuLinkHDWallet = await createWallet(password);

assert(nuLinkHDWallet);

  // we can get the account by user password that we have created
  const accountBob: Account = (await getWalletDefaultAccount(password)) as Account;
  assert(accountBob);

//Bob finds the file Bob has just uploaded
const findFileResultList = (await getOtherShareFiles(accountBob,undefined, false, undefined,
undefined, undefined, 1, 1000
)) as object;

assert(findFileResultList && findFileResultList["total"] > 0);

let fileIndex2 = -1;
for (let index = 0; index < findFileResultList["list"].length; index++) {
  const element = findFileResultList["list"][index];
  if (element["file_name"] === fileList[0]["name"]) {
    fileIndex2 = index;
    break;
  }
}
assert(fileIndex2 >= 0);

const findFileInfo = findFileResultList["list"][fileIndex2];
assert(findFileInfo["owner_id"] === accountAlice.id);

const applyFileId = findFileInfo["file_id"];

//get file details
const fileDetails = (await getFileDetails(applyFileId, accountBob.id)) as object;

//assert(fileDetails["creator_id"] === accountAlice.id);
assert(fileDetails["file_id"] === applyFileId);
assert(parseInt(fileDetails["status"]) === 0); //Is not to apply for

//Bob requests permission to use the file for 7 days
try {
  await applyForFilesUsagePermission([applyFileId], accountBob, 7);
} catch (e) {
  console.log("bob apply file failed", e);
  assert(false);
}

//Alice receives Bob's file usage request
const filesNeedToApprovedResultList = await getFilesPendingApprovalAsPublisher(accountAlice, 1, 1000);

let fileIndex3 = -1;
for (
  let index = 0;
  index < filesNeedToApprovedResultList["list"].length;
  index++
) {
  const element = filesNeedToApprovedResultList["list"][index];
  if (element["file_id"] === applyFileId) {
    fileIndex3 = index;
    break;
  }
}
assert(fileIndex3 >= 0);

assert(filesNeedToApprovedResultList && filesNeedToApprovedResultList["total"] > 0);
const needToApprovedFileInfo =
  filesNeedToApprovedResultList["list"][fileIndex3];
assert(needToApprovedFileInfo["file_owner_id"] === accountAlice.id);

//Alice rejected the file usage request
await refusalApplicationForUseFiles(accountAlice, needToApprovedFileInfo["apply_id"]);

//Bob apply file for usage again. The application period is three days, less than the previous seven days
try {
  await applyForFilesUsagePermission([applyFileId], accountBob, 3);
} catch (e) {
  console.log("bob reapply file failed", e);
  assert(false);
}

//Alice receives Bob's file usage request again
const filesNeedToApprovedResultList2 = await getFilesPendingApprovalAsPublisher(accountAlice, 1, 1000);

assert(
  filesNeedToApprovedResultList2 &&
    filesNeedToApprovedResultList2["total"] > 0
);

let fileIndex4 = -1;
for (
  let index = 0;
  index < filesNeedToApprovedResultList2["list"].length;
  index++
) {
  const element = filesNeedToApprovedResultList2["list"][index];
  if (element["file_id"] === applyFileId) {
    fileIndex4 = index;
    break;
  }
}
assert(fileIndex4 >= 0);

const needToApprovedFileInfo2 = filesNeedToApprovedResultList2["list"][fileIndex4];
assert(needToApprovedFileInfo2["file_owner_id"] === accountAlice.id);

//At this point Alice approves Bob's file usage request, Due to on-chain approval of Bob's request, we first evaluate gas and service fees

//1. Alice calc server fee (wei): the nulink token tnlk/nlk
const startDate: Date = new Date();
const startMs: number = Date.parse(startDate.toString());
const endMs: number =
  startMs + (needToApprovedFileInfo2["days"] as number) * 24 * 60 * 60 * 1000;
const endDate: Date = new Date(endMs); //  start_at is seconds, but Date needs milliseconds

const serverFeeNLKInWei: BigNumber = await getPolicyTokenCost(accountAlice, startDate, endDate, 2);

const serverValue = Web3.utils.fromWei(serverFeeNLKInWei.toString(), "ether");
console.log("server nlk fee  ether is:", serverValue);

//2. Alice calc gas fee (wei): the chain of bsc test token
const gasFeeWei = await getPolicyGasFee(
  accountBob.id,
  needToApprovedFileInfo2["apply_id"],
  2,
  1,
  startMs,
  endMs,
  BigNumber.from(serverFeeNLKInWei)
);

//Note: Please make sure that the account has sufficient tnlk and bsc testnet tokens before this, otherwise the approval will fail
//Alice approves Bob's application for file usage. Whenever Alice approves a file request, an on-chain policy is created
await approvalApplicationForUseFiles(
  accountAlice,
  accountBob.id,
  needToApprovedFileInfo2["apply_id"],
  2,
  1,
  startDate,
  endDate,
  "", //remark
  "", //porterUri
  BigNumber.from(gasFeeWei)
);

//Alice, as the publisher of the file, obtains the list of files that she has successfully approved
const aliceApprovedfilesList = await getApprovedFilesAsPublisher(accountAlice, 1, 1000);

assert(aliceApprovedfilesList && aliceApprovedfilesList["total"] > 0);

let fileIndex5 = -1;
for (let index = 0; index < aliceApprovedfilesList["list"].length; index++) {
  const element = aliceApprovedfilesList["list"][index];
  if (element["file_id"] === applyFileId) {
    fileIndex5 = index;
    break;
  }
}
assert(fileIndex5 >= 0);
const aliceApprovedFileInfo = aliceApprovedfilesList["list"][fileIndex5];
assert(aliceApprovedFileInfo["file_owner_id"] === accountAlice.id);
const policyId = aliceApprovedFileInfo["policy_id"];
console.log("file policy Id:", policyId);

//Bob finds out that his application has been approved by Alice. Bob now has permission to view the contents of the file
const bobBeApprovedfilesList = await getApprovedFilesAsUser(
  accountBob,
  1,
  1000
);

assert(bobBeApprovedfilesList && bobBeApprovedfilesList["total"] > 0);

let fileIndex6 = -1;
for (let index = 0; index < bobBeApprovedfilesList["list"].length; index++) {
  const element = bobBeApprovedfilesList["list"][index];
  if (element["file_id"] === applyFileId) {
    fileIndex6 = index;
    break;
  }
}
assert(fileIndex6 >= 0);

const bobBeApprovedfilesInfo = bobBeApprovedfilesList["list"][fileIndex6];
assert(bobBeApprovedfilesInfo["file_owner_id"] === accountAlice.id);
const policyId2 = bobBeApprovedfilesInfo["policy_id"];
assert(policyId2 === policyId);

//Finally, Bob gets the contents of the file
const arrayBuffer: ArrayBuffer = await getFileContentByFileIdAsUser(
  accountBob,
  bobBeApprovedfilesInfo["file_id"]
);
const fileContent: string = Buffer.from(arrayBuffer).toString();
console.log("fileContent: ", fileContent);
console.log("plainText: ", plainText);
assert(fileContent === plainText);

//finish

// Whenever Alice approves a file request, an on-chain policy is created
// Alice can also obtain the on-chain policy information published by herself
const dataPolicys = await getPublishedPoliciesInfo(accountAlice, 1, 1000);

assert(!isBlank(dataPolicys));

//Alice also can encrypt and update a file to the ipfs network by select an existing on-chain policy
const plainText2 = "This is a philosophy book content";
const historyContent2: Uint8Array = enc.encode(plainText2);

//1.upload file
const fileList2: FileInfo[] = [
  {
    name: `philosophy-${nanoid()}.pdf`,
    fileBinaryArrayBuffer: historyContent2.buffer,
  },
];

//Files uploaded by using published policies do not need approval. Bob can use the files directly, so there is no approval record
const fileIds = await uploadFilesBySelectPolicy(
  accountAlice,
  FileCategory.Philosophy,
  fileList2,
  policyId
);

//Bob can directly download Alice's associated policy upload file without waiting for Alice's approval,
//because the associated policy has already been created and does not need repeated approval. Note: This publish policy value is available for Bob
//Bob get new upload file content
const arrayBuffer2: ArrayBuffer = await getFileContentByFileIdAsUser(
  accountBob,
  fileIds[0]
);
const fileContent2: string = Buffer.from(arrayBuffer2).toString();
console.log("fileContent2: ", fileContent2);
console.log("plainText2: ", plainText2);
assert(fileContent2 === plainText2);

//you can get all status files for mine apply: The files I applied for
//status 0: all status, include:  applying, approved, rejected
const data = (await getFilesByStatus(
  undefined,
  accountBob.id,
  undefined,
  undefined,
  0,
  1,
  1000
)) as object;

assert(data && !isBlank(data) && data["total"] > 0);

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

## More examples

[nulink-sdk-demo](https://github.com/NuLink-network/nulink-sdk-demo)
