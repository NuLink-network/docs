[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getLoginedUserInfo

# Function: getLoginedUserInfo

▸ **getLoginedUserInfo**(): `Promise`<{ `name`: `undefined` \| `string` = account.name; `address`: `undefined` \| `string` = account.address; `id`: `undefined` \| `string` = account.id; `ipfs`: `string` = config.ipfs; `service`: `string` = config.service }\>

get information of the logged-in user
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

#### Returns

`Promise`<{ `name`: `undefined` \| `string` = account.name; `address`: `undefined` \| `string` = account.address; `id`: `undefined` \| `string` = account.id; `ipfs`: `string` = config.ipfs; `service`: `string` = config.service }\>

- The object containing the user information: {"name": , "address": "account address", "id": "account id", "ipfs": "IPFS",  "service": "service URL"}

#### Defined in

[api/pre.ts:114](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/pre.ts#L114)
