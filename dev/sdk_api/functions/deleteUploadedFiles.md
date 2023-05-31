[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / deleteUploadedFiles

# Function: deleteUploadedFiles

▸ **deleteUploadedFiles**(`account`, `fileIds`): `Promise`<`unknown`\>

Deletes the specified files uploaded by the account from the server, This account acts as the publisher

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | The account that owns the files to be deleted. |
| `fileIds` | `string`[] | An array of file IDs to delete. |

#### Returns

`Promise`<`unknown`\>

#### Defined in

[core/pre/api/workflow.ts:529](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L529)
