[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / estimatePolicyGas

# Function: estimatePolicyGas

▸ **estimatePolicyGas**(`publisher`, `userAccountId`, `applyId`, `ursulaShares`, `ursulaThreshold`, `startDate`, `endDate`, `serverFee`, `porterUri?`): `Promise`<`BigNumber`\>

estimate gas fees for sharing files

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `publisher` | [`Account`](../classes/Account.md) | Account the account object of the file publisher (Alice) |
| `userAccountId` | `string` | the account Id of the file publisher (Alice) |
| `applyId` | `string` | The application ID returned to the user by the interface when applying to use a specific file |
| `ursulaShares` | `number` | Number of service shares |
| `ursulaThreshold` | `number` | The file user can download the file after obtaining the specified number of service data shares |
| `startDate` | `Date` | - |
| `endDate` | `Date` | - |
| `serverFee` | `BigNumber` | server fees by call function of `getPolicyServerGasFee` |
| `porterUri?` | `string` | (Optional) the porter service url |

#### Returns

`Promise`<`BigNumber`\>

- the amount of bnb/tbnb in wei

#### Defined in

[core/pre/api/workflow.ts:1287](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L1287)
