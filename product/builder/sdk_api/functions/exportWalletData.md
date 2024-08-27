[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / exportWalletData

# Function: exportWalletData

▸ **exportWalletData**(`password`): `Promise`<`undefined` \| `string`\>

Exports the wallet data as a binary string.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `password` | `string` | The password used to decrypt the wallet. |

#### Returns

`Promise`<`undefined` \| `string`\>

- Returns a binary string of the exported wallet data. Returns undefined if the wallet could not be loaded.

#### Defined in

[api/wallet.ts:149](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/wallet.ts#L149)
