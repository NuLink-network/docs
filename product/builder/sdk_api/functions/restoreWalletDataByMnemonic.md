[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / restoreWalletDataByMnemonic

# Function: restoreWalletDataByMnemonic

▸ **restoreWalletDataByMnemonic**(`newPassword`, `mnemonic`): `Promise`<[`NuLinkHDWallet`](../classes/NuLinkHDWallet.md)\>

Restores an account by the strategies of the account stored in the backend database.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `newPassword` | `string` | The password for the new wallet. |
| `mnemonic` | `string` | The mnemonic phrase used to restore the wallet. |

#### Returns

`Promise`<[`NuLinkHDWallet`](../classes/NuLinkHDWallet.md)\>

- Returns a new NuLinkHDWallet object with the restored account.

#### Defined in

[api/wallet.ts:98](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/wallet.ts#L98)
