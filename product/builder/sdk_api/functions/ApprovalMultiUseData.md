[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / ApprovalMultiUseData

# Function: ApprovalMultiUseData

▸ **ApprovalMultiUseData**(`data`): `Promise`<`any`\>

Approve the user's multi data/file usage request. The batch version of the ApprovalUseData function.
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Object` | the Object of update data. Object be must be have the properties: "userAccountIds" and "applyIds", return null otherwise The input data must include the following fields in the "data" section: |
| `data.userAccountIds` | `string`[] |  |
| `data.applyIds` | `string`[] |  |
| `data.startSecondsArray` | `number`[] | - |
| `data.endSecondsArray` | `number`[] | - |
| `data.ursulaShares` | `number`[] |  |
| `data.ursulaThresholds` | `number`[] |  |
| `data.gasFeeInWei?` | `BigNumber` | (Optional) by call 'getPolicysGasFee', must be the token of the chain (e.g. bnb), not be the nlk |
| `data.gasPrice?` | `BigNumber` | (Optional) the user can set the gas rate manually, and if it is set to 0, the gasPrice is obtained in real time |
| `data.remark?` | `string` | (Optional) remark |

#### Returns

`Promise`<`any`\>

- If the "userAccountIds" and "applyIds" properties are not included in the "data" parameter, return null.
         Otherwise, return the object of
         {
           txHash: 'the transaction hash of the "approve" transaction',
           from: 'publisher.address'
         }

#### Defined in

[api/pre.ts:506](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L506)
