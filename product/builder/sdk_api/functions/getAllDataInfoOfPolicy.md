[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getAllDataInfoOfPolicy

# Function: getAllDataInfoOfPolicy

▸ **getAllDataInfoOfPolicy**(`data`): `Promise`<`unknown`\>

Obtain a list of data/files associated with the policy (including the data/files of both the data/file publisher and the file applicant).

**`Throws`**

ParameterError The input parameter must have the "policyId" field

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Object` | Object must be include the following fields in the "data" section: |
| `data.pageIndex?` | `number` | (Optional) number default 1 |
| `data.pageSize?` | `number` | (Optional) number default 10 |
| `data.policyId` | `string` | policyId |

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

[api/pre.ts:1175](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L1175)
