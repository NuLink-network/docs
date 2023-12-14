[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / NuLinkHDWallet

# Class: NuLinkHDWallet

nulink wallet object

## Table of contents

### Properties

- [accountManager](NuLinkHDWallet.md#accountmanager)

### Methods

- [generateMnemonic](NuLinkHDWallet.md#generatemnemonic)
- [loadHDWallet](NuLinkHDWallet.md#loadhdwallet)
- [existDefaultAccount](NuLinkHDWallet.md#existdefaultaccount)
- [logout](NuLinkHDWallet.md#logout)
- [createHDWallet](NuLinkHDWallet.md#createhdwallet)
- [restoreHDWallet](NuLinkHDWallet.md#restorehdwallet)
- [restoreHDWalletByRootExtendedPrivateKey](NuLinkHDWallet.md#restorehdwalletbyrootextendedprivatekey)
- [restoreWalletDataByRootExtendedPrivateKeyAndServerStrategyInfos](NuLinkHDWallet.md#restorewalletdatabyrootextendedprivatekeyandserverstrategyinfos)
- [restoreWalletDataByMnemonicAndServerStrategyInfos](NuLinkHDWallet.md#restorewalletdatabymnemonicandserverstrategyinfos)
- [restoreHDWalletByData](NuLinkHDWallet.md#restorehdwalletbydata)
- [restoreDataByStrategyInfos](NuLinkHDWallet.md#restoredatabystrategyinfos)
- [recoverUserData](NuLinkHDWallet.md#recoveruserdata)
- [exportUserData](NuLinkHDWallet.md#exportuserdata)
- [exportWalletData](NuLinkHDWallet.md#exportwalletdata)
- [getMnemonic](NuLinkHDWallet.md#getmnemonic)
- [getRootExtendedPrivateKey](NuLinkHDWallet.md#getrootextendedprivatekey)
- [verifyPassword](NuLinkHDWallet.md#verifypassword)
- [getAccountManager](NuLinkHDWallet.md#getaccountmanager)
- [setAccountManager](NuLinkHDWallet.md#setaccountmanager)
- [strategyIds](NuLinkHDWallet.md#strategyids)
- [accountIds](NuLinkHDWallet.md#accountids)
- [dump](NuLinkHDWallet.md#dump)
- [parseUserDataVersionInfo](NuLinkHDWallet.md#parseuserdataversioninfo)
- [load](NuLinkHDWallet.md#load)
- [verifyPasswordAndEncrypt](NuLinkHDWallet.md#verifypasswordandencrypt)
- [encrypt](NuLinkHDWallet.md#encrypt)
- [decrypt](NuLinkHDWallet.md#decrypt)

## Properties

### accountManager

• `Protected` **accountManager**: [`AccountManager`](AccountManager.md)

#### Defined in

[core/hdwallet/api/account.ts:1559](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1559)

## Methods

### generateMnemonic

▸ `Static` **generateMnemonic**(): `string`

Generates a new BIP39 mnemonic phrase.

**`Static`**

**`Memberof`**

NuLinkHDWallet

#### Returns

`string`

- The generated mnemonic phrase as a string.

#### Defined in

[core/hdwallet/api/account.ts:1610](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1610)

___

### loadHDWallet

▸ `Static` **loadHDWallet**(`password?`): `Promise`<``null`` \| [`NuLinkHDWallet`](NuLinkHDWallet.md)\>

The front end loads different pages according to the status returned by this function, whether to display account information or restore the account
 Note:  If no password is passed to the loadHDwallet function, it will attempt to obtain the wallet object from memory.
 If it cannot be obtained, null is returned. In this case, the function needs to be called again with the user's password to retrieve the wallet object.

**`Static`**

**`Throws`**

PasswordDecryptError

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `password` | `string` | `''` | (Optional) If no password is passed to the loadHDwallet function, it will attempt to obtain the wallet object from memory. If it cannot be obtained, null is returned. In this case, the function needs to be called again with the user's password to retrieve the wallet object. |

#### Returns

`Promise`<``null`` \| [`NuLinkHDWallet`](NuLinkHDWallet.md)\>

#### Defined in

[core/hdwallet/api/account.ts:1625](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1625)

___

### existDefaultAccount

▸ `Static` **existDefaultAccount**(): `Promise`<`boolean`\>

Determines whether there is a default account in local storage.

**`Static`**

**`Memberof`**

NuLinkHDWallet

#### Returns

`Promise`<`boolean`\>

- Returns true if a default account exists, false otherwise.

#### Defined in

[core/hdwallet/api/account.ts:1675](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1675)

___

### logout

▸ `Static` **logout**(): `Promise`<`void`\>

Logs out the user by clearing the local storage.

**`Static`**

**`Memberof`**

NuLinkHDWallet

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:1718](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1718)

___

### createHDWallet

▸ `Static` **createHDWallet**(`mnemonic`, `newPassword`): `Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

Creates a new wallet with the specified password and optional mnemonic phrase.
If no mnemonic phrase is provided, one will be generated automatically.
attention please: you need to call the createAccountIfNotExist method outside of this function for add user account to the center server for decouple

**`Static`**

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `mnemonic` | `string` | (Optional) The optional mnemonic phrase used to generate the wallet or generate a mnemonic phrase automatically |
| `newPassword` | `string` | The password used to encrypt the wallet. |

#### Returns

`Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

- Returns a new NuLinkHDWallet object.

#### Defined in

[core/hdwallet/api/account.ts:1732](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1732)

___

### restoreHDWallet

▸ `Static` **restoreHDWallet**(`mnemonic`, `newPassword`, `dataFileBinaryString?`): `Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

Restores a NuLinkHDWallet using a mnemonic phrase and optional data file binary string.
attention please: you need to call the createAccountIfNotExist method outside of this function for add user account to the center server for decouple

**`Throws`**

Error - Throws an error if the restore wallet tag is missing or if the wallet could not be restored from the data file.

**`Static`**

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `mnemonic` | `string` | `undefined` | The mnemonic phrase used to restore the wallet. |
| `newPassword` | `string` | `undefined` | The password used to encrypt the wallet. |
| `dataFileBinaryString?` | `string` | `''` | The optional binary string of a data file to restore the wallet from. The dataFileBinaryString is returned by the exportWalletData function If a data file binary string is provided, the wallet's account data will be restored from it. Otherwise, a new account will be created. |

#### Returns

`Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

- Returns a new NuLinkHDWallet object.

#### Defined in

[core/hdwallet/api/account.ts:1751](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1751)

___

### restoreHDWalletByRootExtendedPrivateKey

▸ `Static` **restoreHDWalletByRootExtendedPrivateKey**(`privateKeyString`, `newPassword`, `dataFileBinaryString?`): `Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

Restores an HDWallet object using a root extended private key and optional user data.

**`Remarks`**

This static method restores an HDWallet object by using a provided root extended private key and optional user data.
If user data is provided, the function attempts to restore accounts and other data associated with the wallet. If no user data is provided,
the function creates a new account. The restored or new HDWallet object is encrypted with the provided password and returned.

attention please: you need to call the createAccountIfNotExist method outside of this function for add user account to the center server for decouple

**`Throws`**

Error  Throws an InvalidRootExtendedPrivateKeyError if the provided private key does not follow the BIP32 standard.

**`Static`**

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `privateKeyString` | `string` | `undefined` | The root extended private key used to generate sub-accounts and access funds. |
| `newPassword` | `string` | `undefined` | The password used to encrypt the HDWallet object. |
| `dataFileBinaryString?` | `string` | `''` | Optional parameter that contains user data, such as account information, in binary form. |

#### Returns

`Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

- An encrypted HDWallet object containing account and user data.

#### Defined in

[core/hdwallet/api/account.ts:1813](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1813)

___

### restoreWalletDataByRootExtendedPrivateKeyAndServerStrategyInfos

▸ `Static` **restoreWalletDataByRootExtendedPrivateKeyAndServerStrategyInfos**(`newPassword`, `rootExtendedPrivateKey`): `Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

restore wallet by the strategys of account stored in the backend db.
attention please: you need to call the createAccountIfNotExist method outside of this function for add user account to the center server for decouple

**`Static`**

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `newPassword` | `string` | new password |
| `rootExtendedPrivateKey` | `string` | BIP32 root Extended PrivateKey. base58Key format：be startwith 'xprv' |

#### Returns

`Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

- Returns a new NuLinkHDWallet object with the restored account.

#### Defined in

[core/hdwallet/api/account.ts:1897](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1897)

___

### restoreWalletDataByMnemonicAndServerStrategyInfos

▸ `Static` **restoreWalletDataByMnemonicAndServerStrategyInfos**(`newPassword`, `mnemonic`): `Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

Restores an account by the strategies of the account stored in the backend database.
attention please: you need to call the createAccountIfNotExist method outside of this function for add user account to the center server for decouple

**`Static`**

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `newPassword` | `string` | The password for the new wallet. |
| `mnemonic` | `string` | The mnemonic phrase used to restore the wallet. |

#### Returns

`Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

- Returns a new NuLinkHDWallet object with the restored account.

#### Defined in

[core/hdwallet/api/account.ts:1914](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1914)

___

### restoreHDWalletByData

▸ `Static` **restoreHDWalletByData**(`newPassword`, `dataFileBinaryString`): `Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

Restores an account by data info (including the mnemonic (or root extended private key) and user data (strategy infos)).

**`Throws`**

UserDataCorruptedError

**`Static`**

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `newPassword` | `string` | The password for the new wallet. |
| `dataFileBinaryString` | `string` | The binary string data file used to restore the wallet. The dataFileBinaryString is returned by the exportWalletData function. |

#### Returns

`Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

- Returns a new NuLinkHDWallet object with the restored account.

#### Defined in

[core/hdwallet/api/account.ts:1934](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1934)

___

### restoreDataByStrategyInfos

▸ **restoreDataByStrategyInfos**(`newPassword`, `_mode?`): `Promise`<`void`\>

Restore data using the strategies of the accounts stored in the backend database.

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `newPassword` | `string` | `undefined` | New password for encryption |
| `_mode` | `DataStrategyRecoveryMode` | `DataStrategyRecoveryMode.Union` | Recovery mode for restoring data strategies |

#### Returns

`Promise`<`void`\>

- Promise object representing the completion of restoring data

#### Defined in

[core/hdwallet/api/account.ts:2025](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2025)

___

### recoverUserData

▸ **recoverUserData**(`newPassword`, `dataFileBinaryString?`, `_mode?`): `Promise`<`void`\>

Recover user data to current NuLinkHDWallet object using the provided encrypted data file.

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `newPassword` | `string` | `undefined` | New password for encryption |
| `dataFileBinaryString` | `string` | `''` | Encrypted data file as a binary string |
| `_mode` | `DataStrategyRecoveryMode` | `DataStrategyRecoveryMode.Union` | Recovery mode for restoring data strategies |

#### Returns

`Promise`<`void`\>

- Promise object representing the completion of recovering user data

#### Defined in

[core/hdwallet/api/account.ts:2070](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2070)

___

### exportUserData

▸ **exportUserData**(`password`): `Promise`<`string`\>

Export user data as an encrypted file.

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `password` | `string` | Password for decrypt nulink wallet |

#### Returns

`Promise`<`string`\>

- Promise object representing the encrypted data file as a string

#### Defined in

[core/hdwallet/api/account.ts:2120](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2120)

___

### exportWalletData

▸ **exportWalletData**(`password`): `Promise`<`string`\>

Exports the wallet data (include user data and mnemonic or private key) as a binary string.

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `password` | `string` | The password used to decrypt the wallet. |

#### Returns

`Promise`<`string`\>

- Returns a binary string of the exported wallet data.

#### Defined in

[core/hdwallet/api/account.ts:2158](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2158)

___

### getMnemonic

▸ **getMnemonic**(`password`): `Promise`<``null`` \| `string`\>

Get the mnemonic phrase for the master account.

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `password` | `string` | Password for decryption |

#### Returns

`Promise`<``null`` \| `string`\>

- Promise object representing the mnemonic phrase for the master account

#### Defined in

[core/hdwallet/api/account.ts:2200](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2200)

___

### getRootExtendedPrivateKey

▸ **getRootExtendedPrivateKey**(`password`): `Promise`<``null`` \| `string`\>

Get the base58 root extend private key for the master account.

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `password` | `string` | Password for decryption |

#### Returns

`Promise`<``null`` \| `string`\>

- Promise object representing the base58 root extend private key for the master account

#### Defined in

[core/hdwallet/api/account.ts:2216](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2216)

___

### verifyPassword

▸ **verifyPassword**(`password`): `Promise`<`boolean`\>

Verifies a password by comparing it to the previously saved hashed password.

**`Throws`**

AssertionError - Throws an error if the hdWallet or passwordHash is blank.

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `password` | `string` | The password to verify. |

#### Returns

`Promise`<`boolean`\>

- Returns true if the password is verified, false otherwise.

#### Defined in

[core/hdwallet/api/account.ts:2257](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2257)

___

### getAccountManager

▸ **getAccountManager**(): [`AccountManager`](AccountManager.md)

Retrieves the AccountManager object associated with the NuLinkHDWallet.

**`Memberof`**

NuLinkHDWallet

#### Returns

[`AccountManager`](AccountManager.md)

#### Defined in

[core/hdwallet/api/account.ts:2281](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2281)

___

### setAccountManager

▸ **setAccountManager**(`_accountManager`): `void`

Set the account manager for the wallet.

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `_accountManager` | [`AccountManager`](AccountManager.md) | Account manager object |

#### Returns

`void`

#### Defined in

[core/hdwallet/api/account.ts:2290](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2290)

___

### strategyIds

▸ **strategyIds**(): `string`[]

Returns an array of strategy IDs associated with all accounts of the current HD wallet instance.

**`Memberof`**

NuLinkHDWallet

#### Returns

`string`[]

- An array of strategy IDs as strings.

#### Defined in

[core/hdwallet/api/account.ts:2552](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2552)

___

### accountIds

▸ **accountIds**(): `string`[]

Returns an array of account IDs associated with all accounts of the current HD wallet instance.

**`Memberof`**

NuLinkHDWallet

#### Returns

`string`[]

- An array of account IDs as strings.

#### Defined in

[core/hdwallet/api/account.ts:2561](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2561)

___

### dump

▸ **dump**(): `Promise`<`string`\>

Returns a JSON string representation of the nulink wallet object.

**`Memberof`**

NuLinkHDWallet

#### Returns

`Promise`<`string`\>

- Returns a JSON string representation of the  nulink wallet object.

#### Defined in

[core/hdwallet/api/account.ts:2570](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2570)

___

### parseUserDataVersionInfo

▸ `Static` **parseUserDataVersionInfo**(`dataFileBinaryString`): `Promise`<`any`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `dataFileBinaryString` | `string` |

#### Returns

`Promise`<`any`\>

#### Defined in

[core/hdwallet/api/account.ts:2598](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2598)

___

### load

▸ `Static` **load**(`jsonString`, `save?`, `recoverPassword?`): `Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

Loads a nulink wallet object from a JSON string.

**`Static`**

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `jsonString` | `string` | `undefined` | The JSON string to parse and load. |
| `save` | `boolean` | `false` | - |
| `recoverPassword?` | `boolean` | `true` | A boolean indicating whether or not to recover the password used to encrypt the HD wallet instance |

#### Returns

`Promise`<[`NuLinkHDWallet`](NuLinkHDWallet.md)\>

- Returns a Promise that resolves with the nulink wallet object.

#### Defined in

[core/hdwallet/api/account.ts:2702](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2702)

___

### verifyPasswordAndEncrypt

▸ **verifyPasswordAndEncrypt**(`plaintext`, `password`): `Promise`<`string`\>

Decrypt the mnemonic phrase or root extended private key using the user's password, denoted as S1. Then, use S1 to generate a password to encrypt the data

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `plaintext` | `string` | {string} - The plaintext data to be encrypted. |
| `password` | `string` | {string} - The user's password used to verify their identity and derive a password for the encryption. |

#### Returns

`Promise`<`string`\>

- A Promise that resolves to the encrypted data as a string.

#### Defined in

[core/hdwallet/api/account.ts:2891](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2891)

___

### encrypt

▸ **encrypt**(`plaintext`): `Promise`<`string`\>

Use the mnemonic phrase or root extended private key to generate a password to encrypt the data

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `plaintext` | `string` | {string} - The plaintext data to be encrypted. |

#### Returns

`Promise`<`string`\>

- A Promise that resolves to the encrypted data as a string.

#### Defined in

[core/hdwallet/api/account.ts:2924](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2924)

___

### decrypt

▸ `Static` **decrypt**(`ciphertext`, `walletSecret`): `Promise`<`string`\>

Decrypts the ciphertext using the wallet secret (mnemonic phrase or root extended private key).

**`Static`**

**`Memberof`**

NuLinkHDWallet

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `ciphertext` | `string` | {string} - The encrypted data to be decrypted. |
| `walletSecret` | `walletSecretKeyType` | {string} - The wallet secret (mnemonic phrase or root extended private key) used to decrypt the data. |

#### Returns

`Promise`<`string`\>

- A Promise that resolves to the decrypted data as a string.

#### Defined in

[core/hdwallet/api/account.ts:2955](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L2955)
