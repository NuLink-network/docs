[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getFileContentAsPublisher

# Function: getFileContentAsPublisher

▸ **getFileContentAsPublisher**(`data`): `Promise`<{ `url`: `string` = url; `fileName`: `string`  }\>

The file publisher obtains the content of the file

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

[api/pre.ts:659](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/pre.ts#L659)
