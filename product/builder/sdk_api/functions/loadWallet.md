[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / loadWallet

# Function: loadWallet

▸ **loadWallet**(`password?`): `Promise`<``null`` \| [`NuLinkHDWallet`](../classes/NuLinkHDWallet.md)\>

The front end loads different pages according to the status returned by this function, whether to display account information or restore the account
Note: If no password is passed to the loadHDwallet function, it will attempt to obtain the wallet object from memory.
If it cannot be obtained, null is returned. In this case, the function needs to be called again with the user's password to retrieve the wallet object.

**`Throws`**

PasswordDecryptError

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `password?` | `string` | (Optional) If no password is passed to the loadHDwallet function, it will attempt to obtain the wallet object from memory. If it cannot be obtained, null is returned. In this case, the function needs to be called again with the user's password to retrieve the wallet object. |

#### Returns

`Promise`<``null`` \| [`NuLinkHDWallet`](../classes/NuLinkHDWallet.md)\>

#### Defined in

[api/wallet.ts:188](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/wallet.ts#L188)
