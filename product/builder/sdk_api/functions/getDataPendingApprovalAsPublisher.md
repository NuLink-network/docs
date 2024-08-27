[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getDataPendingApprovalAsPublisher

# Function: getDataPendingApprovalAsPublisher

▸ **getDataPendingApprovalAsPublisher**(`account`, `pageIndex?`, `pageSize?`): `Promise`<`object`\>

Gets a list of files/data pending approval (applying but not yet approved). This account acts as the publisher (Alice) and needs to approve them.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | `undefined` | (Optional) The current account information. |
| `pageIndex` | `number` | `1` | (Optional) The index of the page to retrieve. Default is 1. |
| `pageSize` | `number` | `10` | (Optional) The number of files/data to retrieve per page. Default is 10. |

#### Returns

`Promise`<`object`\>

- Returns an object containing the list of files/data and pagination information.
                          {
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

[core/pre/api/workflow.ts:948](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L948)
