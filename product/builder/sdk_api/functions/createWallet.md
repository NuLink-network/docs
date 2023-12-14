[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / createWallet

# Function: createWallet

▸ **createWallet**(`password`, `mnemonic?`): `Promise`<[`NuLinkHDWallet`](../classes/NuLinkHDWallet.md)\>

Creates a new wallet with the specified password and optional mnemonic phrase.
If no mnemonic phrase is provided, one will be generated automatically.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `password` | `string` | `undefined` | The password used to encrypt the wallet. |
| `mnemonic` | `string` | `''` | (Optional) The optional mnemonic phrase used to generate the wallet or generate a mnemonic phrase automatically |

#### Returns

`Promise`<[`NuLinkHDWallet`](../classes/NuLinkHDWallet.md)\>

- Returns a new NuLinkHDWallet object.

#### Defined in

[api/wallet.ts:157](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/wallet.ts#L157)
