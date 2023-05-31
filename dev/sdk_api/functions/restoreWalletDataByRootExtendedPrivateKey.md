[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / restoreWalletDataByRootExtendedPrivateKey

# Function: restoreWalletDataByRootExtendedPrivateKey

▸ **restoreWalletDataByRootExtendedPrivateKey**(`newPassword`, `rootExtendedPrivateKey`): `Promise`<[`NuLinkHDWallet`](../classes/NuLinkHDWallet.md)\>

restore wallet by the strategys of account stored in the backend db.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `newPassword` | `string` | new password |
| `rootExtendedPrivateKey` | `string` | BIP32 root Extended PrivateKey. base58Key format：be startwith 'xprv' |

#### Returns

`Promise`<[`NuLinkHDWallet`](../classes/NuLinkHDWallet.md)\>

- Returns a new NuLinkHDWallet object with the restored account.

#### Defined in

[api/wallet.ts:74](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/wallet.ts#L74)
