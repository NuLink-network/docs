[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / revokePermissionApplicationOfFiles

# Function: revokePermissionApplicationOfFiles

▸ **revokePermissionApplicationOfFiles**(`account`, `applyIds`): `Promise`<`unknown`\>

Revokes the permission application of the specified files. This account acts as the user(Bob).
If it has been approved or failed, it can not be revoked.
The background service processing logic is such that if there are multiple permission applications, either all of them will be successful or none of them will be successful.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | The account that revokes the permission application. |
| `applyIds` | `number`[] | An array of application applyIds to revoke. |

#### Returns

`Promise`<`unknown`\>

- Returns an empty object.

#### Defined in

[core/pre/api/workflow.ts:675](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L675)
