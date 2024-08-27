[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / isUserLogined

# Function: isUserLogined

▸ **isUserLogined**(): `Promise`<`boolean`\>

Retrieve if the default account is logged in
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

#### Returns

`Promise`<`boolean`\>

#### Defined in

[api/pre.ts:296](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L296)
