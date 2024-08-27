[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getDataForApprovedAsUser

# Function: getDataForApprovedAsUser

▸ **getDataForApprovedAsUser**(`data`): `Promise`<`object`\>

The data/file applicant retrieves a list of data/files that have been approved for their own use.
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Object` | Object must be include the following fields in the "data" section: |
| `data.pageIndex?` | `number` | (Optional) number default 1 |
| `data.pageSize?` | `number` | (Optional) number default 10 |

#### Returns

`Promise`<`object`\>

- {
               "list": [
                 {
                   "file_id": "8feS-wp5lYhGOCtOLTKZH",
                   "file_name": "1.jpg",
                   "address": " data/file ipfs address: QmV16aK1Ayn5XELdw9oBKK9YEoEDPb9mraPNnJL8XGbZAz",
                   "category": "data/file type category",
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

[api/pre.ts:633](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L633)
