[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / AccountManager

# Class: AccountManager

An account management object that stores all account information.

## Hierarchy

- `IJson`

  ↳ **`AccountManager`**

## Table of contents

### Constructors

- [constructor](AccountManager.md#constructor)

### Properties

- [defaultAccountAddressIndex](AccountManager.md#defaultaccountaddressindex)

### Methods

- [restoreDefaultAccount](AccountManager.md#restoredefaultaccount)
- [load](AccountManager.md#load)
- [loadSaved](AccountManager.md#loadsaved)
- [getAccountCount](AccountManager.md#getaccountcount)
- [getAllAccount](AccountManager.md#getallaccount)
- [getAllAccountSortByAccountId](AccountManager.md#getallaccountsortbyaccountid)
- [createAccount](AccountManager.md#createaccount)
- [removeAccount](AccountManager.md#removeaccount)
- [getAccount](AccountManager.md#getaccount)
- [getAccountByAddress](AccountManager.md#getaccountbyaddress)
- [getDefaultAccount](AccountManager.md#getdefaultaccount)
- [strategyIds](AccountManager.md#strategyids)
- [accountIds](AccountManager.md#accountids)
- [dump](AccountManager.md#dump)
- [serialize](AccountManager.md#serialize)
- [deserialize](AccountManager.md#deserialize)

## Constructors

### constructor

• **new AccountManager**()

#### Inherited from

IJson.constructor

## Properties

### defaultAccountAddressIndex

• **defaultAccountAddressIndex**: `number` = `0`

#### Defined in

[core/hdwallet/api/account.ts:1013](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1013)

## Methods

### restoreDefaultAccount

▸ `Static` **restoreDefaultAccount**(): `Promise`<[`AccountManager`](AccountManager.md)\>

Restores the default account using the strategies stored in the backend database and returns a new AccountManager object.

**`Memberof`**

AccountManager

**`Static`**

#### Returns

`Promise`<[`AccountManager`](AccountManager.md)\>

｛Promise<AccountManager>｝- A Promise that resolves to a new AccountManager object with the default account restored.

#### Defined in

[core/hdwallet/api/account.ts:1381](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1381)

___

### load

▸ `Static` **load**(`jsonString`, `save?`): `Promise`<[`AccountManager`](AccountManager.md)\>

Loads a accountManager object from a JSON string.

**`Static`**

**`Memberof`**

AccountManager

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `jsonString` | `string` | `undefined` | The JSON string to parse and load. |
| `save` | `boolean` | `false` | - |

#### Returns

`Promise`<[`AccountManager`](AccountManager.md)\>

- Returns a Promise that resolves with the accountManager object.

#### Overrides

IJson.load

#### Defined in

[core/hdwallet/api/account.ts:1425](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1425)

___

### loadSaved

▸ `Static` **loadSaved**(): `Promise`<[`AccountManager`](AccountManager.md)\>

**`Static`**

Loads the saved account information from browser local storage and returns a AccountManager object.

**`Memberof`**

AccountManager

#### Returns

`Promise`<[`AccountManager`](AccountManager.md)\>

- A Promise that resolves to a AccountManager object with the saved account information loaded.

#### Defined in

[core/hdwallet/api/account.ts:1463](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1463)

___

### getAccountCount

▸ **getAccountCount**(): `number`

Returns the number of accounts in the account mapping data structure.

**`Memberof`**

AccountManager

#### Returns

`number`

- The number of accounts as a number.

#### Defined in

[core/hdwallet/api/account.ts:1047](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1047)

___

### getAllAccount

▸ **getAllAccount**(): [`Account`](Account.md)[]

Returns an array of all the accounts in the account mapping data structure, sorted by address index in ascending order.

**`Memberof`**

AccountManager

#### Returns

[`Account`](Account.md)[]

- An array of Account objects.

#### Defined in

[core/hdwallet/api/account.ts:1056](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1056)

___

### getAllAccountSortByAccountId

▸ **getAllAccountSortByAccountId**(): [`Account`](Account.md)[]

Returns an array of all the accounts in the account mapping data structure, sorted by account ID in ascending order.

**`Memberof`**

AccountManager

#### Returns

[`Account`](Account.md)[]

- An array of Account objects.

#### Defined in

[core/hdwallet/api/account.ts:1067](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1067)

___

### createAccount

▸ **createAccount**(`name?`, `defaultAccount?`): `Promise`<[`Account`](Account.md)\>

Creates a new account and returns it.

**`Memberof`**

AccountManager

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `name` | `string` | `''` | {string} - (optional) The name of the account . |
| `defaultAccount` | `boolean` | `false` | {boolean} - (optional) Whether to set the new account as the default account (optional, defaults to false). |

#### Returns

`Promise`<[`Account`](Account.md)\>

- A Promise that resolves to the newly created Account object.

#### Defined in

[core/hdwallet/api/account.ts:1125](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1125)

___

### removeAccount

▸ **removeAccount**(`addressIndex`): `Promise`<`undefined` \| [`Account`](Account.md)\>

Removes an account with the specified address index and returns it.

**`Memberof`**

AccountManager

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `addressIndex` | `number` | {number} - The address index of the account to be removed. |

#### Returns

`Promise`<`undefined` \| [`Account`](Account.md)\>

- A Promise that resolves to the removed Account object, or undefined if the account does not exist or cannot be removed.

#### Defined in

[core/hdwallet/api/account.ts:1169](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1169)

___

### getAccount

▸ **getAccount**(`index`): `undefined` \| [`Account`](Account.md)

Returns the Account object with the specified address index, or undefined if the account does not exist.

**`Memberof`**

AccountManager

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `index` | `number` | {number} - The address index of the account to be retrieved. |

#### Returns

`undefined` \| [`Account`](Account.md)

- The Account object with the specified address index, or undefined if the account does not exist.

#### Defined in

[core/hdwallet/api/account.ts:1308](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1308)

___

### getAccountByAddress

▸ **getAccountByAddress**(`address`): `undefined` \| [`Account`](Account.md)

Returns the Account object with the specified address, or undefined if the account does not exist.

**`Memberof`**

AccountManager

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `address` | `string` | {string} - The address index of the account to be retrieved. |

#### Returns

`undefined` \| [`Account`](Account.md)

- The Account object with the specified address, or undefined if the account does not exist.

#### Defined in

[core/hdwallet/api/account.ts:1318](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1318)

___

### getDefaultAccount

▸ **getDefaultAccount**(): `undefined` \| [`Account`](Account.md)

Retrieves the default account associated with the NuLinkHDWallet.
If no default account is set, the account with index 0 will be returned.

**`Memberof`**

AccountManager

#### Returns

`undefined` \| [`Account`](Account.md)

- Returns the default account or undefined if it does not exist.

#### Defined in

[core/hdwallet/api/account.ts:1336](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1336)

___

### strategyIds

▸ **strategyIds**(): `string`[]

Returns an array of strategy IDs associated with all accounts of the current HD wallet instance.

**`Memberof`**

AccountManager

#### Returns

`string`[]

- An array of strategy IDs as strings.

#### Defined in

[core/hdwallet/api/account.ts:1346](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1346)

___

### accountIds

▸ **accountIds**(): `string`[]

Returns an array of account IDs associated with all accounts of the current HD wallet instance.

**`Memberof`**

AccountManager

#### Returns

`string`[]

- An array of account IDs as strings.

#### Defined in

[core/hdwallet/api/account.ts:1363](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1363)

___

### dump

▸ **dump**(): `string`

Returns a JSON string representation of the AccountManager object.

**`Memberof`**

AccountManager

#### Returns

`string`

- Returns a JSON string representation of the AccountManager object.

#### Overrides

IJson.dump

#### Defined in

[core/hdwallet/api/account.ts:1401](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1401)

___

### serialize

▸ **serialize**(): `Promise`<`void`\>

Serializes the accountManager object and encrypts it to 'Browser-local storage'.

**`Memberof`**

AccountManager

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:1551](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1551)

___

### deserialize

▸ **deserialize**(): `Promise`<[`AccountManager`](AccountManager.md)\>

Deserializes a accountManager object from 'Browser-local storage' by decrypting it and creating a account object in memory.

**`Memberof`**

AccountManager

#### Returns

`Promise`<[`AccountManager`](AccountManager.md)\>

- Returns a Promise that resolves with the deserialized accountManager object.

#### Defined in

[core/hdwallet/api/account.ts:1561](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L1561)
