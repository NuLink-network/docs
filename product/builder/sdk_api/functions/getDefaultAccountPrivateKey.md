[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getDefaultAccountPrivateKey

# Function: getDefaultAccountPrivateKey

▸ **getDefaultAccountPrivateKey**(`password?`): `Promise`<``null`` \| `string`\>

get the wallet's mnemonic
 Note:  If no password is passed to the getWalletDefaultAccount function, it will attempt to obtain the wallet object from memory.
 If it cannot be obtained, null is returned. In this case, the function needs to be called again with the user's password to retrieve the wallet object.

**`Throws`**

PasswordDecryptError

#### Parameters

| Name | Type |
| :------ | :------ |
| `password?` | `string` |

#### Returns

`Promise`<``null`` \| `string`\>

- Returns the privateKey of the default account if the password is correct, otherwise returns null.

#### Defined in

[api/wallet.ts:289](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/wallet.ts#L289)
