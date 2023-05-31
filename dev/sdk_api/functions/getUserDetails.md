[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / getUserDetails

# Function: getUserDetails

▸ **getUserDetails**(): `Promise`<`unknown`\>

Retrieve user information details
Please unlock account with your password first by call getWalletDefaultAccount(userpassword), otherwise an UnauthorizedError exception will be thrown.

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

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

[api/pre.ts:166](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/api/pre.ts#L166)
