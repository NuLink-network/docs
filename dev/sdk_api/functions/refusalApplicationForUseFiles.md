[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / refusalApplicationForUseFiles

# Function: refusalApplicationForUseFiles

▸ **refusalApplicationForUseFiles**(`publisher`, `applyId`, `remark?`): `Promise`<`unknown`\>

Rejects the application for the use of files. This account acts as the publisher (Alice).

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `publisher` | [`Account`](../classes/Account.md) | `undefined` | The account of the publisher (Alice). |
| `applyId` | `string` | `undefined` | The application apply ID to reject. |
| `remark` | `string` | `''` | (Optional) Additional remarks for the rejection. Default is an empty string. |

#### Returns

`Promise`<`unknown`\>

#### Defined in

[core/pre/api/workflow.ts:1681](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L1681)
