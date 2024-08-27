[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getDataByApplyStatusAsUser

# Function: getDataByApplyStatusAsUser

▸ **getDataByApplyStatusAsUser**(`account`, `status?`, `pageIndex?`, `pageSize?`): `Promise`<`object`\>

The file/data applicant retrieves a list of files/data in a specified state that need to be approved by others.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | `undefined` | the current account object |
| `status` | `number` | `0` | (Optional) default 0: All state 1: Under review, 2: Approved, 3: Rejected, 4: Under approval, 5: Expired |
| `pageIndex` | `number` | `1` | (Optional) number default 1 |
| `pageSize` | `number` | `10` | (Optional) number default 10 |

#### Returns

`Promise`<`object`\>

- {
               "list": [
                 {
                   "file_id": "8feS-wp5lYhGOCtOLTKZH",
                   "file_name": "1.jpg",
                   "address": " file/data ipfs address: QmV16aK1Ayn5XELdw9oBKK9YEoEDPb9mraPNnJL8XGbZAz",
                   "category": "file/data type category",
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

[core/pre/api/workflow.ts:1071](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L1071)
