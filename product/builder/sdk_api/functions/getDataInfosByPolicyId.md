[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getDataInfosByPolicyId

# Function: getDataInfosByPolicyId

▸ **getDataInfosByPolicyId**(`policyId`, `policyPublisherId?`, `policyUserId?`, `pageIndex?`, `pageSize?`): `Promise`<`unknown`\>

Gets the file/data information associated with the published policy (so the policy has been published)

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `policyId` | `string` | `undefined` | policyId |
| `policyPublisherId?` | `string` | `undefined` | (Optional) The account id of the file/data publisher, acting as the role of file/data publisher |
| `policyUserId?` | `string` | `undefined` | (Optional) The account id of the file/data user, acting as the role of file/data applicant Only one of the two parameters, "policyPublisherId" and "policyUserId", can be selected, or neither of them can be passed |
| `pageIndex` | `number` | `1` | (Optional) number default 1 |
| `pageSize` | `number` | `10` | (Optional) number default 10 |

#### Returns

`Promise`<`unknown`\>

- {
               "list": [
                 {
                   "file_id": "Data/File ID",
                   "file_name": "Data/File name",
                   "owner": "Data/File owner",
                   "owner_id": "Data/File owner account ID",
                   "owner_avatar": "Data/File owner avatar",
                   "address": "Data/File address",
                   "thumbnail": "Data/File thumbnail",
                   "created_at": "Data/File upload timestamp",
                   "policy_id": "Policy ID",
                   "policy_hrac": "Policy HRAC",
                   "policy_start_at": "Policy start timestamp",
                   "policy_end_at": "Policy end timestamp",
                 },
                 ...
             ],
             "total": total count
           }

#### Defined in

[core/pre/api/workflow.ts:2934](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L2934)
