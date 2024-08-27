[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getPolicyServerFee

# Function: getPolicyServerFee

▸ **getPolicyServerFee**(`startSeconds`, `endSeconds`, `ursulaShares`): `Promise`<`string`\>

get service fees (NLK/TNLK) for sharing data/files
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `startSeconds` | `number` | Start time of data/file usage application in seconds |
| `endSeconds` | `number` | End time of data/file usage application in seconds |
| `ursulaShares` | `number` | Number of service shares |

#### Returns

`Promise`<`string`\>

- the amount of NLK/TNLK in wei

#### Defined in

[api/pre.ts:35](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L35)
