[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getWalletDefaultAccount

# Function: getWalletDefaultAccount

▸ **getWalletDefaultAccount**(`password?`): `Promise`<``null`` \| [`Account`](../classes/Account.md)\>

get the default account from wallet
 Note: If no password is passed to the getWalletDefaultAccount function, it will attempt to obtain the wallet object from memory.
 If it cannot be obtained, null is returned. In this case, the function needs to be called again with the user's password to retrieve the wallet object.

**`Throws`**

PasswordDecryptError

#### Parameters

| Name | Type |
| :------ | :------ |
| `password?` | `string` |

#### Returns

`Promise`<``null`` \| [`Account`](../classes/Account.md)\>

#### Defined in

[api/wallet.ts:237](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/wallet.ts#L237)
