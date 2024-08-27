[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getWalletDefaultAccount

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

[api/wallet.ts:247](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/wallet.ts#L247)
