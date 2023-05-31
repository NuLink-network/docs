[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getApprovedFileContentUrl

# Function: getApprovedFileContentUrl

▸ **getApprovedFileContentUrl**(`data`): `Promise`<{ `url`: `string` = url; `fileName`: `string`  }\>

The file applicant retrieves the content of a file that has been approved for their usage.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

**`Throws`**

ParameterError The input parameter must have the "fileId" field

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Object` | Object must be include the following fields in the "data" section: |
| `data.fileId` | `string` |  |
| `data.fileName` | `string` |  |

#### Returns

`Promise`<{ `url`: `string` = url; `fileName`: `string`  }\>

- { url: "file content url", fileName: "file name" }

#### Defined in

[api/pre.ts:598](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/pre.ts#L598)
