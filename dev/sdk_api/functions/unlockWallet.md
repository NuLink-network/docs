[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / unlockWallet

# Function: unlockWallet

▸ **unlockWallet**(`password`): `Promise`<`boolean`\>

Attempts to unlock the NuLinkHDWallet with the given password.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `password` | `string` | The password used to decrypt the wallet. |

#### Returns

`Promise`<`boolean`\>

- Returns true if the password is correct, false otherwise.

#### Defined in

[api/wallet.ts:259](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/wallet.ts#L259)
