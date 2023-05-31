[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getUploadedFiles

# Function: getUploadedFiles

▸ **getUploadedFiles**(`account`, `fileName?`, `pageIndex?`, `pageSize?`): `Promise`<`unknown`\>

Gets a list of files uploaded by the specified account from the server. This account acts as the publisher

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | `undefined` | The account to retrieve the file list for. |
| `fileName?` | `string` | `undefined` | (Optional) The name of the file to search for. Leave blank to retrieve all files. |
| `pageIndex` | `number` | `1` | (Optional) The index of the page to retrieve. Default is 1. |
| `pageSize` | `number` | `10` | (Optional) The number of files to retrieve per page. Default is 10. |

#### Returns

`Promise`<`unknown`\>

- Returns an object containing the list of files and pagination information.
            {
                list: [
                  {
                    {string} file_id - File ID
                    {string} file_name - File name
                    {string} owner - File owner
                    {string} owner_id - File owner account ID
                    {string} address - File address
                    {string} thumbnail - File thumbnail
                    {number} created_at - File upload timestamp
                  },
                  ...
                ],
                total: total cnt
            }

#### Defined in

[core/pre/api/workflow.ts:473](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L473)
