[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / applyForFilesUsagePermission

# Function: applyForFilesUsagePermission

▸ **applyForFilesUsagePermission**(`fileIds`, `account`, `usageDays?`): `Promise`<`unknown`\>

Applies for file usage permission for the specified files, This account acts as the user(Bob).

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `fileIds` | `string`[] | `undefined` | An array of file IDs to apply for usage permission. |
| `account` | [`Account`](../classes/Account.md) | `undefined` | The account that applies for the permission. |
| `usageDays` | `number` | `7` | (Optional) The validity period of the application, in days. Default is 7. |

#### Returns

`Promise`<`unknown`\>

#### Defined in

[core/pre/api/workflow.ts:636](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L636)
