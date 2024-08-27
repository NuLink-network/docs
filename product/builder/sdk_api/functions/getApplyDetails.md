[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getApplyDetails

# Function: getApplyDetails

▸ **getApplyDetails**(`applyId`): `Promise`<``null`` \| `object`\>

Gets the details of an application record.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `applyId` | `string` | The ID of the application record. |

#### Returns

`Promise`<``null`` \| `object`\>

- Returns an object containing the details of the application record, or null if the record does not exist.
             {
               start_at:  "The start timestamp of the application",
               end_at: "The end timestamp of the application",
               policy_label: "The label of the policy",
               policy_label_id: "The ID of the policy label",
               days: "days",
               status: "apply status: 1 - In progress, 2 - Approved, 3 - Rejected, 4 - Under review, 5 - Expired, 6 - Approve Failed"
             }

#### Defined in

[core/pre/api/workflow.ts:3186](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L3186)
