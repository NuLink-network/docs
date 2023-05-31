[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getFileContentAsUser

# Function: getFileContentAsUser

▸ **getFileContentAsUser**(`userAccount`, `policyEncryptingKey`, `aliceVerifyingKey`, `fileIPFSAddress`, `encryptedTreasureMapIPFSAddress`, `porterUri?`): `Promise`<`ArrayBuffer`\>

Gets the content of an approved file, which can be downloaded. The input parameter is obtained by calling getApprovedFilesAsUser (Account).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `userAccount` | [`Account`](../classes/Account.md) | The current account information. |
| `policyEncryptingKey` | `string` | The policy encrypting key used to encrypt the file. |
| `aliceVerifyingKey` | `string` | The Alice verifying key used to verify the policy. |
| `fileIPFSAddress` | `string` | The IPFS address of the file to download. |
| `encryptedTreasureMapIPFSAddress` | `string` | The IPFS address of the encrypted treasure map. |
| `porterUri?` | `string` | The URI of the porter node. Default is undefined, and will be retrieved from the API. |

#### Returns

`Promise`<`ArrayBuffer`\>

- Returns the file content as an ArrayBuffer.

#### Defined in

[core/pre/api/workflow.ts:1798](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L1798)
