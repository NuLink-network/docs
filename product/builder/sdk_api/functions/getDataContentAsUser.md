[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getDataContentAsUser

# Function: getDataContentAsUser

▸ **getDataContentAsUser**(`userAccount`, `policyEncryptingKey`, `aliceVerifyingKey`, `dataIPFSAddress`, `encryptedTreasureMapIPFSAddress`, `crossChainHrac`, `porterUri?`): `Promise`<`ArrayBuffer`\>

Gets the content of an approved file/data, which can be downloaded. The input parameter is obtained by calling getApprovedDataAsUser (Account).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `userAccount` | [`Account`](../classes/Account.md) | The current account information. |
| `policyEncryptingKey` | `string` | The policy encrypting key used to encrypt the file/data. |
| `aliceVerifyingKey` | `string` | The Alice verifying key used to verify the policy. |
| `dataIPFSAddress` | `string` | The IPFS address of the file/data to download. |
| `encryptedTreasureMapIPFSAddress` | `string` | The IPFS address of the encrypted treasure map. |
| `crossChainHrac` | `CrossChainHRAC` | - |
| `porterUri?` | `string` | The URI of the porter node. Default is undefined, and will be retrieved from the API. |

#### Returns

`Promise`<`ArrayBuffer`\>

- Returns the file/data content as an ArrayBuffer.

#### Defined in

[core/pre/api/workflow.ts:3008](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L3008)
