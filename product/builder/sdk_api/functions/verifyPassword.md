[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / verifyPassword

# Function: verifyPassword

▸ **verifyPassword**(`password`): `Promise`<`undefined` \| `boolean`\>

Verifies a password by comparing it to the previously saved hashed password.

**`Throws`**

AssertionError - Throws an error if the hdWallet or passwordHash is blank.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `password` | `string` | The password to verify. |

#### Returns

`Promise`<`undefined` \| `boolean`\>

- Returns true if the password is verified, false otherwise. Returns undefined if the wallet could not be retrieved.

#### Defined in

[api/wallet.ts:202](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/wallet.ts#L202)
