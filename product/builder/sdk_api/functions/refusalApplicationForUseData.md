[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / refusalApplicationForUseData

# Function: refusalApplicationForUseData

▸ **refusalApplicationForUseData**(`publisher`, `applyId`, `remark?`): `Promise`<`unknown`\>

Rejects the application for the use of files/data. This account acts as the publisher (Alice).

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `publisher` | [`Account`](../classes/Account.md) | `undefined` | The account of the publisher (Alice). |
| `applyId` | `string` | `undefined` | The application apply ID to reject. |
| `remark` | `string` | `''` | (Optional) Additional remarks for the rejection. Default is an empty string. |

#### Returns

`Promise`<`unknown`\>

#### Defined in

[core/pre/api/workflow.ts:2862](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L2862)
