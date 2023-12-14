[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / uploadFilesBySelectPolicy

# Function: uploadFilesBySelectPolicy

▸ **uploadFilesBySelectPolicy**(`account`, `fileCategory`, `fileList`, `policyId`): `Promise`<`string`[]\>

Uploads files to the server by selecting an existing policy and uploading the files encrypted with the policy's public key to IPFS.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | The account to use to upload the files. |
| `fileCategory` | `string` \| [`FileCategory`](../enums/FileCategory.md) | The category of the files being uploaded. Must be a valid FileCategory value or a string. |
| `fileList` | [`FileInfo`](../types/FileInfo.md)[] | The list of files to upload. Each element of the array must be an object with properties 'name' and 'fileBinaryArrayBuffer'. |
| `policyId` | `number` | The ID of the policy to use to encrypt and upload the files. |

#### Returns

`Promise`<`string`[]\>

- Returns an array of file IDs uploaded to the server.

#### Defined in

[core/pre/api/workflow.ts:354](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L354)
