[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getPolicyInfosAsUser

# Function: getPolicyInfosAsUser

▸ **getPolicyInfosAsUser**(`data`): `Promise`<`object`\>

The applicant of the file obtains a list of the policy information
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Object` | Object must be include the following fields in the "data" section: |
| `data.pageIndex?` | `number` | (Optional) number default 1 |
| `data.pageSize?` | `number` | (Optional) number default 10 |

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

[api/pre.ts:1064](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L1064)
