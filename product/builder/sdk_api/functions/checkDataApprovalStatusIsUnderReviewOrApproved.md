[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / checkDataApprovalStatusIsUnderReviewOrApproved

# Function: checkDataApprovalStatusIsUnderReviewOrApproved

▸ **checkDataApprovalStatusIsUnderReviewOrApproved**(`data`): `Promise`<``null`` \| `number`\>

Check if the application status is "under review" or "approved"

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Object` | Object be must be have the property of "applyId", return null otherwise |
| `data.applyId` | `string` | The ID of the data/file application. |

#### Returns

`Promise`<``null`` \| `number`\>

- return 2: approved , 4: approving(Under review) , <0: not approved and approving(Under review),  return null otherwise.

#### Defined in

[api/pre.ts:401](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L401)
