[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / approvalApplicationForUseData

# Function: approvalApplicationForUseData

▸ **approvalApplicationForUseData**(`publisher`, `userAccountId`, `applyId`, `ursulaShares`, `ursulaThreshold`, `startDate`, `endDate`, `remark?`, `porterUri?`, `gasFeeInWei?`, `gasPrice?`): `Promise`<`any`\>

Approval of application for use of Files/Data, This account acts as Publisher (Alice) grant
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `publisher` | [`Account`](../classes/Account.md) | `undefined` | Account the current account object |
| `userAccountId` | `string` | `undefined` | string |
| `applyId` | `string` | `undefined` | string |
| `ursulaShares` | `number` | `undefined` | number |
| `ursulaThreshold` | `number` | `undefined` | number |
| `startDate` | `Date` | `undefined` | policy usage start date |
| `endDate` | `Date` | `undefined` | policy usage end date |
| `remark` | `string` | `''` | (Optional) |
| `porterUri` | `string` | `''` | (Optional) the porter services url |
| `gasFeeInWei` | `BigNumber` | `undefined` | (Optional) by call 'getPolicyGasFee', must be the token of the chain (e.g. bnb), not be the nlk |
| `gasPrice` | `BigNumber` | `undefined` | (Optional) the user can set the gas rate manually, and if it is set to 0, the gasPrice is obtained in real time |

#### Returns

`Promise`<`any`\>

- {
                      txHash: 'the transaction hash of the "approve" transaction',
                      from: 'publisher.address'
                    }

#### Defined in

[core/pre/api/workflow.ts:2228](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L2228)
