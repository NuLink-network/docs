[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getPolicyTokenCost

# Function: getPolicyTokenCost

▸ **getPolicyTokenCost**(`publisher`, `startDate`, `endDate`, `ursulaShares`): `Promise`<`BigNumber`\>

calcurate publish policy server fee (nlk/tnlk): By calling calcPolicyCost

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `publisher` | [`Account`](../classes/Account.md) | the current logined Account object |
| `startDate` | `Date` | - |
| `endDate` | `Date` | - |
| `ursulaShares` | `number` | Number of service shares |

#### Returns

`Promise`<`BigNumber`\>

- the amount of NLK/TNLK in wei

#### Defined in

[core/pre/api/workflow.ts:1227](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L1227)
