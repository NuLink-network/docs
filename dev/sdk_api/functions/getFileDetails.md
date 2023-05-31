[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getFileDetails

# Function: getFileDetails

▸ **getFileDetails**(`fileId`, `fileUserAccountId`): `Promise`<`unknown`\>

Retrieves the details of a file (include apply file info, file info, about policy info) by its ID and user account ID.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `fileId` | `string` | The ID of the file to retrieve details for. |
| `fileUserAccountId` | `string` | This parameter passes the file finder when the file consumer is not known, fileUserAccountId should be passed the current account I |

#### Returns

`Promise`<`unknown`\>

- The returned object contains the following properties:
                  {
                  file_id: string,
                  file_name: string,
                  thumbnail: string,
                  file_created_at: number,
                  apply_id: string,
                  status: number, "Application status, where 0 means not applied, 1 means in progress, 2 approved, and 3 means rejected"
                  apply_start_at: number,
                  apply_end_at: number,
                  apply_created_at: number,
                  policy_id: string,
                  hrac: string,
                  creator: string,
                  creator_id: string,
                  consumer: string,
                  consumer_id: string,
                  gas: number,
                  tx_hash: string,
                  policy_created_at: number,
                  file_ipfs_address: string,
                  policy_encrypted_pk: string,
                  encrypted_treasure_map_ipfs_address: string,
                  alice_verify_pk: string
                  }

#### Defined in

[core/pre/api/workflow.ts:1990](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L1990)
