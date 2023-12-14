[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / AccountManager

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

[core/hdwallet/api/account.ts:989](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L989)

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

[core/hdwallet/api/account.ts:1339](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1339)

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

[core/hdwallet/api/account.ts:1383](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1383)

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

[core/hdwallet/api/account.ts:1421](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1421)

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

[core/hdwallet/api/account.ts:1023](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1023)

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

[core/hdwallet/api/account.ts:1032](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1032)

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

[core/hdwallet/api/account.ts:1043](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1043)

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

[core/hdwallet/api/account.ts:1101](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1101)

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

[core/hdwallet/api/account.ts:1145](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1145)

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

[core/hdwallet/api/account.ts:1284](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1284)

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

[core/hdwallet/api/account.ts:1294](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1294)

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

[core/hdwallet/api/account.ts:1304](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1304)

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

[core/hdwallet/api/account.ts:1321](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1321)

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

[core/hdwallet/api/account.ts:1359](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1359)

___

### serialize

▸ **serialize**(): `Promise`<`void`\>

Serializes the accountManager object and encrypts it to 'Browser-local storage'.

**`Memberof`**

AccountManager

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:1509](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1509)

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

[core/hdwallet/api/account.ts:1519](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L1519)
