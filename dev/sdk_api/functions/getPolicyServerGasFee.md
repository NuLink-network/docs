[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getPolicyServerGasFee

# Function: getPolicyServerGasFee

▸ **getPolicyServerGasFee**(`startSeconds`, `endSeconds`, `ursulaShares`): `Promise`<`string`\>

get service fees (NLK/TNLK) for sharing files
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `startSeconds` | `number` | Start time of file usage application in seconds |
| `endSeconds` | `number` | End time of file usage application in seconds |
| `ursulaShares` | `number` | Number of service shares |

#### Returns

`Promise`<`string`\>

- the amount of NLK/TNLK in wei

#### Defined in

[api/pre.ts:28](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/pre.ts#L28)
