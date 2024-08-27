[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / uploadDataByCreatePolicy

# Function: uploadDataByCreatePolicy

▸ **uploadDataByCreatePolicy**(`account`, `category`, `dataInfoList`): `Promise`<[`Strategy`](../classes/Strategy.md)\>

Uploads files/data to the server by creating a new local policy and uploading the files/data encrypted with the policy's public key to IPFS.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | The account to use to create the policy and upload the files/data. |
| `category` | `string` \| [`DataCategory`](../enums/DataCategory.md) | The category of the files/data being uploaded. Must be a valid DataCategory value or a string. |
| `dataInfoList` | [`DataInfo`](../types/DataInfo.md)[] | The list of files/data to upload. Each element of the array must be an object with properties 'label' and 'dataArrayBuffer'. |

#### Returns

`Promise`<[`Strategy`](../classes/Strategy.md)\>

- Returns the strategy used to upload the files/data.

#### Defined in

[core/pre/api/workflow.ts:334](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L334)
