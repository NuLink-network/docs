[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / getAccountInfos

# Function: getAccountInfos

▸ **getAccountInfos**(`accountIds`): `Promise`<`object`[]\>

get account infos by multiple account ids

#### Parameters

| Name | Type |
| :------ | :------ |
| `accountIds` | `string`[] |

#### Returns

`Promise`<`object`[]\>

- account information details list

        [ {
             name	string	account name
             account_id	string	account ID(UUID v4)
             ethereum_addr	string	eth address
             encrypted_pk	string	encrypted PK
             verify_pk	string	verifyed PK
             status	number	account state 
             created_at	number	account create time
             avatar           string  IPFS address of avatar
             name         string  nickname            
             user_site         string  Address of the user's primary site   
             twitter          string  twitter address     
             instagram        string  instagram address  
             facebook         string  facebook address    
             profile string  personal data        
         },
         ...
       ]

#### Defined in

[core/pre/api/workflow.ts:243](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/pre/api/workflow.ts#L243)
