[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getPublishedPoliciesInfo

# Function: getPublishedPoliciesInfo

▸ **getPublishedPoliciesInfo**(`account`, `pageIndex?`, `pageSize?`): `Promise`<`object`\>

The publisher of the file obtains a list of the information of the policies published on the blockchain.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `account` | [`Account`](../classes/Account.md) | `undefined` |  |
| `pageIndex` | `number` | `1` | (Optional) number default 1 |
| `pageSize` | `number` | `10` | (Optional) number default 10 |

#### Returns

`Promise`<`object`\>

- {
               "list": [
                 {
                   "hrac":"Policy hrac",
                   "policy_id":"Policy ID",
                   "creator":"Policy creator",
                   "creator_id":"Policy creator ID",
                   "creator_address":"Ethereum address of the policy creator",
                   "consumer":"Policy consumer",
                   "consumer_id":"Policy consumer ID",
                   "consumer_address":"Ethereum address of the policy consumer",
                   "gas":"Gas fee in wei",
                   "tx_hash":"Transaction hash",
                   "encrypted_pk":"Policy encryption public key",
                   "start_at":"Policy start timestamp",
                   "end_at":"Policy end timestamp",
                   "created_at":"Policy creation timestamp"
                 },
                 ...
             ],
             "total": total count
           }

#### Defined in

[core/pre/api/workflow.ts:1141](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L1141)
