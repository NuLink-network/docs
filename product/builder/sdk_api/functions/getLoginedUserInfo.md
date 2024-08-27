[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getLoginedUserInfo

# Function: getLoginedUserInfo

▸ **getLoginedUserInfo**(): `Promise`<{ `name`: `undefined` \| `string` = account.name; `address`: `undefined` \| `string` = account.address; `id`: `undefined` \| `string` = account.id; `service`: `string` = config.service; `chainId`: `number` = config.chainId; `chainName`: `string` = config.chainName }\>

get information of the logged-in user
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

#### Returns

`Promise`<{ `name`: `undefined` \| `string` = account.name; `address`: `undefined` \| `string` = account.address; `id`: `undefined` \| `string` = account.id; `service`: `string` = config.service; `chainId`: `number` = config.chainId; `chainName`: `string` = config.chainName }\>

- The object containing the user information: {"name": , "address": "account address", "id": "account id",  "service": "service URL"}

#### Defined in

[api/pre.ts:269](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L269)
