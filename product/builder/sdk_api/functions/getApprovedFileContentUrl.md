[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getApprovedFileContentUrl

# Function: getApprovedFileContentUrl

▸ **getApprovedFileContentUrl**(`data`): `Promise`<{ `url`: `string` = url; `dataLabel`: `string`  }\>

The data/file applicant retrieves the content of a data/file that has been approved for their usage.
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

**`Throws`**

ParameterError The input parameter must have the "dataId" field

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Object` | Object must be include the following fields in the "data" section: |
| `data.dataId` | `string` |  |
| `data.dataLabel` | `string` |  |

#### Returns

`Promise`<{ `url`: `string` = url; `dataLabel`: `string`  }\>

- { url: "data content url", dataLabel: "data label" }

#### Defined in

[api/pre.ts:848](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L848)
