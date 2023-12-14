[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / restoreWalletData

# Function: restoreWalletData

▸ **restoreWalletData**(`newPassword`, `dataFileBinaryString`): `Promise`<[`NuLinkHDWallet`](../classes/NuLinkHDWallet.md)\>

Restores an account by data info (including the mnemonic (or root extended private key) and user data (strategy infos)).

**`Throws`**

UserDataCorruptedError, UserDataVersionLowError

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `newPassword` | `string` | The password for the new wallet. |
| `dataFileBinaryString` | `string` | The binary string data file used to restore the wallet. The dataFileBinaryString is returned by the exportWalletData function. |

#### Returns

`Promise`<[`NuLinkHDWallet`](../classes/NuLinkHDWallet.md)\>

- Returns a new NuLinkHDWallet object with the restored account.

#### Defined in

[api/wallet.ts:115](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/wallet.ts#L115)
