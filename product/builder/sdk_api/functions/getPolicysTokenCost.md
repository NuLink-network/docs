[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getPolicysTokenCost

# Function: getPolicysTokenCost

▸ **getPolicysTokenCost**(`publisher`, `startDates`, `endDates`, `ursulaShares`): `Promise`<`BigNumber`\>

Calculating service fees (nlk/tnlk) for publishing multiple policys. : By calling calcPolicysCost

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `publisher` | [`Account`](../classes/Account.md) | the current logined Account object |
| `startDates` | `Date`[] | An array of the start time of file/data usage application in seconds |
| `endDates` | `Date`[] | An array of the end time of file/data usage application in seconds |
| `ursulaShares` | `number`[] | An array of the number of service shares |

#### Returns

`Promise`<`BigNumber`\>

- All services fees of the amount of NLK/TNLK in wei

#### Defined in

[core/pre/api/workflow.ts:1418](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L1418)
