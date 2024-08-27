[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getDataDetails

# Function: getDataDetails

▸ **getDataDetails**(`dataId`, `dataUserAccountId`): `Promise`<`unknown`\>

Retrieves the details of a file/data (include apply file/data info, file/data info, about policy info) by its ID and user account ID.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `dataId` | `string` | The ID of the file/data to retrieve details for. |
| `dataUserAccountId` | `string` | This parameter passes the file/data finder when the file/data consumer is not known, dataUserAccountId should be passed the current account I |

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

[core/pre/api/workflow.ts:3289](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L3289)
