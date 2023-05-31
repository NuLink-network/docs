[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / updateUserInfo

# Function: updateUserInfo

▸ **updateUserInfo**(`data`): `Promise`<`unknown`\>

update info of current user account

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Object` | the Object of update data. The input data must be one or more fields in the "data" section |
| `data.avatar?` | `string` | (Optional) the photo of current account |
| `data.nickname?` | `string` | (Optional) the nickname of current account |
| `data.userSite?` | `string` | (Optional) the user site of current account |
| `data.twitter?` | `string` | (Optional) the twitter of current account |
| `data.instagram?` | `string` | (Optional) the instagram of current account |
| `data.facebook?` | `string` | (Optional) the facebook of current account |
| `data.personalProfile?` | `string` | (Optional) the personal profile of current account Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown. |

#### Returns

`Promise`<`unknown`\>

#### Defined in

[api/pre.ts:219](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/pre.ts#L219)
