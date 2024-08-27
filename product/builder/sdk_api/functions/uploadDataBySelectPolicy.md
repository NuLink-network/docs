[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / uploadDataBySelectPolicy

# Function: uploadDataBySelectPolicy

▸ **uploadDataBySelectPolicy**(`account`, `category`, `dataList`, `policyId`): `Promise`<`string`[]\>

Uploads files/data to the server by selecting an existing policy and uploading the files/data encrypted with the policy's public key to IPFS.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | The account to use to upload the files/data. |
| `category` | `string` \| [`DataCategory`](../enums/DataCategory.md) | The category of the files/data being uploaded. Must be a valid DataCategory value or a string. |
| `dataList` | [`DataInfo`](../types/DataInfo.md)[] | The list of files/data to upload. Each element of the array must be an object with properties 'name' and 'dataArrayBuffer'. |
| `policyId` | `number` | The ID of the policy to use to encrypt and upload the files/data. |

#### Returns

`Promise`<`string`[]\>

- Returns an array of file/data IDs uploaded to the server.

#### Defined in

[core/pre/api/workflow.ts:470](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L470)
