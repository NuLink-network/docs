[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getFilesByStatus

# Function: getFilesByStatus

▸ **getFilesByStatus**(`fileId?`, `proposerId?`, `fileOwnerId?`, `applyId?`, `status?`, `pageIndex?`, `pageSize?`): `Promise`<`object`\>

get files info by status This account acts as the user (Bob) or publisher (Alice)

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `fileId?` | `string` | `undefined` | - |
| `proposerId?` | `string` | `undefined` | (Optional) proposer's account id |
| `fileOwnerId?` | `string` | `undefined` | (Optional) account id of the file owner |
| `applyId?` | `string` | `undefined` | (Optional) to apply for id |
| `status` | `number` | `1` | (Optional) number default 1 1 - In progress, 2 - Approved, 3 - Rejected, 4 - Under review, 5 - Expired. |
| `pageIndex` | `number` | `1` | (Optional) number default 1 |
| `pageSize` | `number` | `10` | (Optional) number default 10 |

#### Returns

`Promise`<`object`\>

- {
               "list": [
                 {
                   "file_id": "8feS-wp5lYhGOCtOLTKZH",
                   "file_name": "1.jpg",
                   "address": " file ipfs address: QmV16aK1Ayn5XELdw9oBKK9YEoEDPb9mraPNnJL8XGbZAz",
                   "category": "file type category",
                   "format": "image",
                   "suffix": "jpg",
                   "owner": "account name",
                   "owner_id": "1b79f5def27bebcc71a71058a7771cc476769fc5dba32f45bcdc1b8c6e353917",
                   "owner_avatar": "Profile picture",
                   "thumbnail": "thumbnail mimetype and ipfs address: image/jpeg|QmUmCdMxu2MnnCmodc5VvnLqqoJn21s2M2LQqV9T5zDgYy",
                   "created_at": 1684116370
                 },
                 ...
             ],
             "total": total count
           }

#### Defined in

[core/pre/api/workflow.ts:1021](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L1021)
