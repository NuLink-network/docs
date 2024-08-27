[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getPolicysGasFee

# Function: getPolicysGasFee

▸ **getPolicysGasFee**(`userAccountIds`, `applyIds`, `ursulaShares`, `ursulaThresholds`, `startSeconds`, `endSeconds`, `serverFee`, `gasPrice?`): `Promise`<[`GasInfo`](../types/GasInfo.md)\>

estimate service gas fees for sharing data/files. The batch version of the getPolicyGasFee function.
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

**`Throws`**

PolicyHasBeenActivedOnChain Policy has been actived(created) on chain (policy is currently active)

**`Throws`**

PolicyApproving Policy are under review, please wait for the review to complete

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `userAccountIds` | `string`[] | the account Id of the data/file applicant (Bob) |
| `applyIds` | `string`[] | The application ID returned to the user by the interface when applying to use a specific data/file |
| `ursulaShares` | `number`[] | Number of service shares |
| `ursulaThresholds` | `number`[] | - |
| `startSeconds` | `number`[] | Start time of data/file usage application in UTC seconds |
| `endSeconds` | `number`[] | End time of data/file usage application in UTC seconds |
| `serverFee` | `BigNumber` | server fees by call function of `getPolicysServerFee` |
| `gasPrice` | `BigNumber` | the user can set the gas rate manually, and if it is set to 0, the gasPrice is obtained in real time |

#### Returns

`Promise`<[`GasInfo`](../types/GasInfo.md)\>

- the GasInfo of bnb/tbnb in wei

#### Defined in

[api/pre.ts:191](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L191)
