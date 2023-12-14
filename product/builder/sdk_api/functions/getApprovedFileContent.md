[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getApprovedFileContent

# Function: getApprovedFileContent

▸ **getApprovedFileContent**(`fileId`): `Promise`<`ArrayBuffer`\>

The file applicant retrieves the content of a file that has been approved for their usage.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

**`Throws`**

ParameterError The input parameter must have the "fileId" field

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `fileId` | `any` | file's id |

#### Returns

`Promise`<`ArrayBuffer`\>

#### Defined in

[api/pre.ts:631](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/pre.ts#L631)
