[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getFilesInfoOfPolicy

# Function: getFilesInfoOfPolicy

▸ **getFilesInfoOfPolicy**(`data`): `Promise`<`unknown`\>

Obtain a list of files associated with the published policy information.
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

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
| `data.asPublisher?` | `boolean` | (Optional) default true true: acting as the role of file publisher. false: acting as the role of file applicant |

#### Returns

`Promise`<`unknown`\>

- {
               "list": [
                 {
                   "file_id": "File ID",
                   "file_name": "File name",
                   "owner": "File owner",
                   "owner_id": "File owner account ID",
                   "owner_avatar": "File owner avatar",
                   "address": "File address",
                   "thumbnail": "File thumbnail",
                   "created_at": "File upload timestamp",
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

[api/pre.ts:861](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/pre.ts#L861)
