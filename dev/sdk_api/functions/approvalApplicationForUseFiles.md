[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / approvalApplicationForUseFiles

# Function: approvalApplicationForUseFiles

▸ **approvalApplicationForUseFiles**(`publisher`, `userAccountId`, `applyId`, `ursulaShares`, `ursulaThreshold`, `startDate`, `endDate`, `remark?`, `porterUri?`, `gasFeeInWei?`): `Promise`<`any`\>

Approval of application for use of Files, This account acts as Publisher (Alice) grant
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
| `gasFeeInWei` | `BigNumber` | `undefined` | - |

#### Returns

`Promise`<`any`\>

- {
                      txHash: 'the transaction hash of the "approve" transaction',
                      from: 'publisher.address'
                    }

#### Defined in

[core/pre/api/workflow.ts:1537](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L1537)
