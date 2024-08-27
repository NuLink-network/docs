[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / checkDataApprovalStatusIsApprovedOrApproving

# Function: checkDataApprovalStatusIsApprovedOrApproving

▸ **checkDataApprovalStatusIsApprovedOrApproving**(`applyId`): `Promise`<`number`\>

Check if the application status is "under review" or "approved"

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `applyId` | `string` \| `number` | string \| number |

#### Returns

`Promise`<`number`\>

Promise<number> - return 2: approved , 4: approving(Under review) , <0: not approved and approving(Under review)

#### Defined in

[core/pre/api/workflow.ts:2155](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L2155)
