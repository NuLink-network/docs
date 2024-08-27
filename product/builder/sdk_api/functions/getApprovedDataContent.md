[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getApprovedDataContent

# Function: getApprovedDataContent

▸ **getApprovedDataContent**(`dataId`): `Promise`<`ArrayBuffer`\>

The data/file applicant retrieves the content of a data/file that has been approved for their usage.
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

**`Throws`**

ParameterError The input parameter must have the "dataId" field

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `dataId` | `any` | data's id |

#### Returns

`Promise`<`ArrayBuffer`\>

#### Defined in

[api/pre.ts:881](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L881)
