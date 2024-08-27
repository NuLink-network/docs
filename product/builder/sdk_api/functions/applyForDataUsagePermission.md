[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / applyForDataUsagePermission

# Function: applyForDataUsagePermission

▸ **applyForDataUsagePermission**(`dataId`, `account`, `usageDays?`): `Promise`<`unknown`\>

Apply for single file/data usage permission for the specified file/data, This account acts as the user(Bob).
Note: Different from applying for the interface with multiple files (apply/files): 
         If the policy corresponding to the document has already been applied for, it will return code: 4109, msg: "current file does not need to apply"

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `dataId` | `string` | `undefined` | A file ID to apply for usage permission. |
| `account` | [`Account`](../classes/Account.md) | `undefined` | The account that applies for the permission. |
| `usageDays` | `number` | `7` | (Optional) The validity period of the application, in days. Default is 7. |

#### Returns

`Promise`<`unknown`\>

#### Defined in

[core/pre/api/workflow.ts:791](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L791)
