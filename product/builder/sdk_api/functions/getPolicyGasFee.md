[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getPolicyGasFee

# Function: getPolicyGasFee

▸ **getPolicyGasFee**(`userAccountId`, `applyId`, `ursulaShares`, `ursulaThreshold`, `startSeconds`, `endSeconds`, `serverFee`, `gasPrice?`): `Promise`<[`GasInfo`](../types/GasInfo.md)\>

estimate service gas fees for sharing data/files
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
| `userAccountId` | `string` | the account Id of the data/file applicant (Bob) |
| `applyId` | `string` | The application ID returned to the user by the interface when applying to use a specific data/file |
| `ursulaShares` | `number` | Number of service shares |
| `ursulaThreshold` | `number` | The data/file user can download the data/file after obtaining the specified number of service data shares |
| `startSeconds` | `number` | Start time of data/file usage application in seconds |
| `endSeconds` | `number` | End time of data/file usage application in seconds |
| `serverFee` | `BigNumber` | server fees by call function of `getPolicyServerFee` |
| `gasPrice` | `BigNumber` | the user can set the gas rate manually, and if it is set to 0, the gasPrice is obtained in real time |

#### Returns

`Promise`<[`GasInfo`](../types/GasInfo.md)\>

- the GasInfo of bnb/tbnb in wei

#### Defined in

[api/pre.ts:124](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L124)
