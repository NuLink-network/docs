[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getUserByAccountId

# Function: getUserByAccountId

▸ **getUserByAccountId**(`data`): `Promise`<`unknown`\>

Retrieve user information details by user account Id

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Object` | Object be must be have the property of "accountId", null otherwise |
| `data.accountId` | `string` | account's Id |

#### Returns

`Promise`<`unknown`\>

- User information details:
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

[api/pre.ts:199](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/pre.ts#L199)
