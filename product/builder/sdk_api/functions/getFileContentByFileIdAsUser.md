[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getFileContentByFileIdAsUser

# Function: getFileContentByFileIdAsUser

▸ **getFileContentByFileIdAsUser**(`userAccount`, `fileId`): `Promise`<`ArrayBuffer`\>

Get approved document content (downloadable). The file applicant retrieves the content of a file that has been approved for their usage.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `userAccount` | [`Account`](../classes/Account.md) | Account the current account object |
| `fileId` | `string` | file's id |

#### Returns

`Promise`<`ArrayBuffer`\>

#### Defined in

[core/pre/api/workflow.ts:1853](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L1853)
