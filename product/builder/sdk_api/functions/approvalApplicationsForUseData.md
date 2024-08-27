[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / approvalApplicationsForUseData

# Function: approvalApplicationsForUseData

▸ **approvalApplicationsForUseData**(`publisher`, `userAccountIds`, `applyIds`, `ursulaShares`, `ursulaThresholds`, `startDates`, `endDates`, `remark?`, `porterUri?`, `gasFeeInWei?`, `gasPrice?`): `Promise`<`any`\>

Approval of applications for use of Files/Data, This account acts as Publisher (Alice) grant. The batch version of the function refusalApplicationForUseData.
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `publisher` | [`Account`](../classes/Account.md) | `undefined` | Account the current account object |
| `userAccountIds` | `string`[] | `undefined` | string |
| `applyIds` | `string`[] | `undefined` | string |
| `ursulaShares` | `number`[] | `undefined` | number |
| `ursulaThresholds` | `number`[] | `undefined` | number |
| `startDates` | `Date`[] | `undefined` | policy usage start date |
| `endDates` | `Date`[] | `undefined` | policy usage end date |
| `remark` | `string` | `''` | (Optional) |
| `porterUri` | `string` | `''` | (Optional) the porter services url |
| `gasFeeInWei` | `BigNumber` | `undefined` | (Optional) by call 'getPolicysGasFee', must be the token of the chain (e.g. bnb), not be the nlk |
| `gasPrice` | `BigNumber` | `undefined` | (Optional) the user can set the gas rate manually, and if it is set to 0, the gasPrice is obtained in real time |

#### Returns

`Promise`<`any`\>

- {
                      txHash: 'the transaction hash of the "approve" transaction',
                      from: 'publisher.address'
                    }

#### Defined in

[core/pre/api/workflow.ts:2536](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L2536)
