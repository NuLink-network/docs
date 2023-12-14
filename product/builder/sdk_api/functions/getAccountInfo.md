[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getAccountInfo

# Function: getAccountInfo

▸ **getAccountInfo**(`accountId`): `Promise`<`unknown`\>

get account info by account id

#### Parameters

| Name | Type |
| :------ | :------ |
| `accountId` | `string` |

#### Returns

`Promise`<`unknown`\>

- account information details
         {
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
         }

#### Defined in

[core/pre/api/workflow.ts:153](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/pre/api/workflow.ts#L153)
