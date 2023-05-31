[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getOtherShareFiles

# Function: getOtherShareFiles

▸ **getOtherShareFiles**(`account`, `fileName?`, `include?`, `fileCategory?`, `fileType?`, `descOrder?`, `pageIndex?`, `pageSize?`): `Promise`<`unknown`\>

Gets a list of files shared by others (files uploaded by the current account are not included). This account acts as the user(Bob).

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | `undefined` | The current account information. |
| `fileName?` | `string` | `undefined` | (Optional) The name of the file to search for. support fuzzy query. Leave blank to retrieve all files. |
| `include?` | `boolean` | `undefined` | Indicates whether the query result contains file list data of the current account. |
| `fileCategory?` | `string` \| [`FileCategory`](../enums/FileCategory.md) | `undefined` | (Optional) The category of the file to search for. |
| `fileType?` | [`FileType`](../enums/FileType.md) | `undefined` | (Optional) The type of the file to search for. |
| `descOrder` | `boolean` | `true` | (Optional) Whether to sort by upload time in reverse order. |
| `pageIndex` | `number` | `1` | (Optional) The index of the page to retrieve. Default is 1. |
| `pageSize` | `number` | `10` | (Optional) The number of files to retrieve per page. Default is 10. |

#### Returns

`Promise`<`unknown`\>

- Returns an object containing the list of files and pagination information.
                        {
                            total: number
                            list: [{
                                file_id: string - File ID
                                file_name: string - File name
                                category: string - File category/type
                                format: string - File format
                                suffix: string - File suffix
                                address: string - File address
                                thumbnail: string - File thumbnail
                                owner: string - File owner
                                owner_id: string - File owner's account ID
                                owner_avatar: string - File owner's avatar
                                created_at: number - File upload timestamp
                            }]
                        }

#### Defined in

[core/pre/api/workflow.ts:579](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L579)
