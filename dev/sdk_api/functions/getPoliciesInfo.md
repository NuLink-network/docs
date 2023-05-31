[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getPoliciesInfo

# Function: getPoliciesInfo

▸ **getPoliciesInfo**(`policyId?`, `creatorId?`, `consumerId?`, `policyLabelId?`, `pageIndex?`, `pageSize?`): `Promise`<`unknown`\>

Obtains a list of the information of the policies published on the blockchain.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `policyId?` | `number` | `undefined` | policyId |
| `creatorId?` | `string` | `undefined` | the publisher's account id of the file |
| `consumerId?` | `string` | `undefined` | the user's account id of the file |
| `policyLabelId?` | `string` | `undefined` | the `label` fields of the Strategy object in the Account Object |
| `pageIndex` | `number` | `1` | (Optional) number default 1 |
| `pageSize` | `number` | `10` | (Optional) number default 10 |

#### Returns

`Promise`<`unknown`\>

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

[core/pre/api/workflow.ts:1180](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L1180)
