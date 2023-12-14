[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / checkFileApprovalStatusIsUnderReviewOrApproved

# Function: checkFileApprovalStatusIsUnderReviewOrApproved

▸ **checkFileApprovalStatusIsUnderReviewOrApproved**(`data`): `Promise`<``null`` \| `boolean`\>

Check if the application status is "under review" or "approved"

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Object` | Object be must be have the property of "applyId", return null otherwise |
| `data.applyId` | `string` | The ID of the file application. |

#### Returns

`Promise`<``null`` \| `boolean`\>

param data Object be must be have the property of "applyId",  return null otherwise.
          Return true if the status is "under review" or "approved", false otherwise

#### Defined in

[api/pre.ts:240](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/pre.ts#L240)
