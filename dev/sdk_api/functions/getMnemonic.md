[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getMnemonic

# Function: getMnemonic

▸ **getMnemonic**(`password?`): `Promise`<`undefined` \| ``null`` \| `string`\>

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

`Promise`<`undefined` \| ``null`` \| `string`\>

Returns the mnemonic phrase if the password is correct, otherwise returns null. Returns undefined if the wallet could not be loaded.

#### Defined in

[api/wallet.ts:276](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/wallet.ts#L276)
