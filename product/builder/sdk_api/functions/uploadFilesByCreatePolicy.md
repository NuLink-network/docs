[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / uploadFilesByCreatePolicy

# Function: uploadFilesByCreatePolicy

▸ **uploadFilesByCreatePolicy**(`account`, `fileCategory`, `fileList`): `Promise`<[`Strategy`](../classes/Strategy.md)\>

Uploads files to the server by creating a new local policy and uploading the files encrypted with the policy's public key to IPFS.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | The account to use to create the policy and upload the files. |
| `fileCategory` | `string` \| [`FileCategory`](../enums/FileCategory.md) | The category of the files being uploaded. Must be a valid FileCategory value or a string. |
| `fileList` | [`FileInfo`](../types/FileInfo.md)[] | The list of files to upload. Each element of the array must be an object with properties 'name' and 'fileBinaryArrayBuffer'. |

#### Returns

`Promise`<[`Strategy`](../classes/Strategy.md)\>

- Returns the strategy used to upload the files.

#### Defined in

[core/pre/api/workflow.ts:229](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L229)
