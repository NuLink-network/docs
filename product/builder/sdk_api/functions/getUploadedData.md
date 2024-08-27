[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getUploadedData

# Function: getUploadedData

▸ **getUploadedData**(`account`, `dataLabel?`, `pageIndex?`, `pageSize?`): `Promise`<`unknown`\>

Gets a list of files/data uploaded by the specified account from the server. This account acts as the publisher

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | `undefined` | The account to retrieve the file/data list for. |
| `dataLabel?` | `string` | `undefined` | (Optional) The name of the file/data to search for. Leave blank to retrieve all files/data. |
| `pageIndex` | `number` | `1` | (Optional) The index of the page to retrieve. Default is 1. |
| `pageSize` | `number` | `10` | (Optional) The number of files/data to retrieve per page. Default is 10. |

#### Returns

`Promise`<`unknown`\>

- Returns an object containing the list of files/data and pagination information.
            {
                list: [
                  {
                    {string} file_id - Data ID
                    {string} file_name - Data name
                    {string} owner - Data owner
                    {string} owner_id - Data owner account ID
                    {string} address - Data address
                    {string} thumbnail - Data thumbnail
                    {number} created_at - Data upload timestamp
                  },
                  ...
                ],
                total: total cnt
            }

#### Defined in

[core/pre/api/workflow.ts:584](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L584)
