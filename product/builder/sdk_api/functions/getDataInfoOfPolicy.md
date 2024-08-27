[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getDataInfoOfPolicy

# Function: getDataInfoOfPolicy

▸ **getDataInfoOfPolicy**(`data`): `Promise`<`unknown`\>

Obtain a list of data/files associated with the published policy information.
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

**`Throws`**

ParameterError The input parameter must have the "policyId" field

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Object` | Object must be include the following fields in the "data" section: |
| `data.pageIndex?` | `number` | (Optional) number default 1 |
| `data.pageSize?` | `number` | (Optional) number default 10 |
| `data.policyId` | `string` | policyId |
| `data.asPublisher?` | `boolean` | (Optional) default true true: acting as the role of data/file publisher. false: acting as the role of data/file applicant |

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

[api/pre.ts:1115](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L1115)
