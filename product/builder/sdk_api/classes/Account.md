[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / Account

# Class: Account

Account class manages account information, include pk/sk key pair info, policy info and so on

## Hierarchy

- `IJson`

  ↳ **`Account`**

## Table of contents

### Constructors

- [constructor](Account.md#constructor)

### Properties

- [name](Account.md#name)
- [address](Account.md#address)
- [addressIndex](Account.md#addressindex)
- [id](Account.md#id)
- [encryptedKeyPair](Account.md#encryptedkeypair)
- [verifyKeyPair](Account.md#verifykeypair)

### Methods

- [setStrategyMapping](Account.md#setstrategymapping)
- [getStrategyInfo](Account.md#getstrategyinfo)
- [createStrategyByLabel](Account.md#createstrategybylabel)
- [createStrategy](Account.md#createstrategy)
- [deleteStrategy](Account.md#deletestrategy)
- [getAllStrategy](Account.md#getallstrategy)
- [getAllStrategySortByStategyId](Account.md#getallstrategysortbystategyid)
- [getAccountStrategyByStategyId](Account.md#getaccountstrategybystategyid)
- [getStrategy](Account.md#getstrategy)
- [getStrategyByLabel](Account.md#getstrategybylabel)
- [strategyIds](Account.md#strategyids)
- [dump](Account.md#dump)
- [restoreByStrategyInfos](Account.md#restorebystrategyinfos)
- [load](Account.md#load)
- [loadSaved](Account.md#loadsaved)
- [serialize](Account.md#serialize)
- [deserialize](Account.md#deserialize)
- [saveAccountItselfInfo](Account.md#saveaccountitselfinfo)
- [getSavedAccountItselfInfo](Account.md#getsavedaccountitselfinfo)
- [removeSavedAccountItselfInfo](Account.md#removesavedaccountitselfinfo)
- [saveAccountAllStrategyIndexInfo](Account.md#saveaccountallstrategyindexinfo)
- [getSavedAccountAllStrategyIndexInfo](Account.md#getsavedaccountallstrategyindexinfo)
- [removeSavedAccountAllStrategyIndexInfo](Account.md#removesavedaccountallstrategyindexinfo)
- [saveAccountAllStrategyInfo](Account.md#saveaccountallstrategyinfo)
- [removeSavedAccountAllStrategyInfo](Account.md#removesavedaccountallstrategyinfo)
- [balance](Account.md#balance)
- [refreshBalance](Account.md#refreshbalance)
- [getNLKBalance](Account.md#getnlkbalance)
- [refreshNLKBalance](Account.md#refreshnlkbalance)

## Constructors

### constructor

• **new Account**(`name`, `addressIndex`, `id?`)

Constructs a new policy object with the specified name, address index, and optional ID.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `name` | `string` | `undefined` | The name of the account. |
| `addressIndex` | `number` | `undefined` | The index of the Ethereum address associated with the account. Generate by generateAddressIndex() function |
| `id?` | `string` | `''` | The optional ID of the account. Generate a account id if the parameter is not passed. |

#### Overrides

IJson.constructor

#### Defined in

[core/hdwallet/api/account.ts:314](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L314)

## Properties

### name

• **name**: `string` = `''`

#### Defined in

[core/hdwallet/api/account.ts:299](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L299)

___

### address

• **address**: `string` = `''`

#### Defined in

[core/hdwallet/api/account.ts:300](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L300)

___

### addressIndex

• **addressIndex**: `number` = `-1`

#### Defined in

[core/hdwallet/api/account.ts:301](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L301)

___

### id

• **id**: `string` = `''`

#### Defined in

[core/hdwallet/api/account.ts:302](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L302)

___

### encryptedKeyPair

• **encryptedKeyPair**: `KeyPair`

#### Defined in

[core/hdwallet/api/account.ts:303](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L303)

___

### verifyKeyPair

• **verifyKeyPair**: `KeyPair`

#### Defined in

[core/hdwallet/api/account.ts:304](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L304)

## Methods

### setStrategyMapping

▸ **setStrategyMapping**(`_strategyMapping`): `void`

Sets the policy mapping for this object for save the policy info to this account

**`Memberof`**

Account

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `_strategyMapping` | `Map`<`number`, [`Strategy`](Strategy.md)\> | The new policy mapping. key: policy index, value: Policy object |

#### Returns

`void`

#### Defined in

[core/hdwallet/api/account.ts:347](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L347)

___

### getStrategyInfo

▸ **getStrategyInfo**(`strategyId`): ``null`` \| [`Strategy`](Strategy.md)

Gets the policy object associated with the specified ID from the policy mapping.

**`Memberof`**

Account

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `strategyId` | `string` | The ID of the policy object to retrieve. |

#### Returns

``null`` \| [`Strategy`](Strategy.md)

- Returns the policy object associated with the specified ID, or null if the ID is not found in the policy mapping.

#### Defined in

[core/hdwallet/api/account.ts:401](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L401)

___

### createStrategyByLabel

▸ **createStrategyByLabel**(`label`): `Promise`<[`Strategy`](Strategy.md)\>

Creates a new policy object with the specified label and a generated ID. The policy object is used to encrypt files uploaded by the user.

**`Memberof`**

Account

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `label` | `string` | The label to use for the new policy. |

#### Returns

`Promise`<[`Strategy`](Strategy.md)\>

- Returns a Promise that resolves with the new policy object.

#### Defined in

[core/hdwallet/api/account.ts:420](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L420)

___

### createStrategy

▸ **createStrategy**(`label`, `id?`): `Promise`<[`Strategy`](Strategy.md)\>

Creates a new policy object with the specified label and ID, and adds it to the policy mapping. The policy object is used to encrypt files uploaded by the user.

**`Memberof`**

Account

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `label` | `string` | `undefined` | The label to use for the new policy. |
| `id?` | `string` | `''` | The optional ID to use for the new policy, If the ID parameter is not passed, it will automatically call the generateStrategyAddressIndex function to generate a new address index for the policy object. |

#### Returns

`Promise`<[`Strategy`](Strategy.md)\>

- Returns a Promise that resolves with the new policy object.

#### Defined in

[core/hdwallet/api/account.ts:434](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L434)

___

### deleteStrategy

▸ **deleteStrategy**(`strategyAddressIndex`): `Promise`<`void`\>

Deletes the policy object associated with the specified address index from the policy mapping.
attention please: If the policy is deleted, address_index can be reused, because if the key generation tree path is certain, the public and private keys must be the same.
                  But note that the ids are not the same, the resources shared in the background cannot be reused

**`Memberof`**

Account

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `strategyAddressIndex` | `number` | The address index of the policy object to delete. |

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:456](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L456)

___

### getAllStrategy

▸ **getAllStrategy**(): [`Strategy`](Strategy.md)[]

Gets an array of all policy objects in the policy mapping, sorted by their address indices in ascending order.

**`Memberof`**

Account

#### Returns

[`Strategy`](Strategy.md)[]

- Returns an array of all policy objects in the policy mapping.

#### Defined in

[core/hdwallet/api/account.ts:486](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L486)

___

### getAllStrategySortByStategyId

▸ **getAllStrategySortByStategyId**(): [`Strategy`](Strategy.md)[]

Gets an array of all policy objects in the policy mapping, sorted by their IDs in ascending order.

**`Memberof`**

Account

#### Returns

[`Strategy`](Strategy.md)[]

- Returns an array of all policy objects in the policy mapping.

#### Defined in

[core/hdwallet/api/account.ts:498](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L498)

___

### getAccountStrategyByStategyId

▸ **getAccountStrategyByStategyId**(`strategyId`): `undefined` \| [`Strategy`](Strategy.md)

Get all policy object associated with the specified account's policy id.

**`Memberof`**

Account

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `strategyId` | `string` | The policy ID of a specified account. |

#### Returns

`undefined` \| [`Strategy`](Strategy.md)

- Returns the policy object associated with the specified ID, or undefined if the ID is not found in the policy mapping.

#### Defined in

[core/hdwallet/api/account.ts:511](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L511)

___

### getStrategy

▸ **getStrategy**(`strategyAddressIndex`): `undefined` \| [`Strategy`](Strategy.md)

Retrieves a policy by its address index.

**`Memberof`**

Account

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `strategyAddressIndex` | `number` | The index of the policy address. |

#### Returns

`undefined` \| [`Strategy`](Strategy.md)

The corresponding policy object, or undefined if no such policy exists.

#### Defined in

[core/hdwallet/api/account.ts:528](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L528)

___

### getStrategyByLabel

▸ **getStrategyByLabel**(`label`): `undefined` \| [`Strategy`](Strategy.md)

Returns the policy object with the given label.

**`Memberof`**

Account

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `label` | `string` | The label of the policy to fetch. |

#### Returns

`undefined` \| [`Strategy`](Strategy.md)

- The policy object if found, otherwise undefined.

#### Defined in

[core/hdwallet/api/account.ts:538](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L538)

___

### strategyIds

▸ **strategyIds**(): `string`[]

Retrieves an array of all policy IDs in the mapping.

**`Memberof`**

Account

#### Returns

`string`[]

- An array of policy IDs.

#### Defined in

[core/hdwallet/api/account.ts:555](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L555)

___

### dump

▸ **dump**(): `string`

Returns a JSON string representation of the current account object.

**`Memberof`**

Account

#### Returns

`string`

- Returns a JSON string representation of the current account object.

#### Overrides

IJson.dump

#### Defined in

[core/hdwallet/api/account.ts:572](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L572)

___

### restoreByStrategyInfos

▸ `Static` **restoreByStrategyInfos**(): `Promise`<[`Account`](Account.md)\>

Restores an account using the strategies stored in the backend database.

**`Static`**

**`Memberof`**

Account

#### Returns

`Promise`<[`Account`](Account.md)\>

- A Promise that resolves to an `Account` object.

#### Defined in

[core/hdwallet/api/account.ts:625](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L625)

___

### load

▸ `Static` **load**(`jsonString`, `save?`): `Promise`<[`Account`](Account.md)\>

Loads a account object from a JSON string.

**`Static`**

**`Memberof`**

Account

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `jsonString` | `string` | `undefined` | The JSON string to parse and load. |
| `save` | `boolean` | `false` | - |

#### Returns

`Promise`<[`Account`](Account.md)\>

- Returns a Promise that resolves with the loaded account object.

#### Overrides

IJson.load

#### Defined in

[core/hdwallet/api/account.ts:668](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L668)

___

### loadSaved

▸ `Static` **loadSaved**(`addressIndex`): `Promise`<``null`` \| [`Account`](Account.md)\>

Deserializes a account object from 'Browser-local storage' by decrypting it and creating a account object in memory.

**`Static`**

**`Memberof`**

Account

#### Parameters

| Name | Type |
| :------ | :------ |
| `addressIndex` | `number` |

#### Returns

`Promise`<``null`` \| [`Account`](Account.md)\>

- Returns a Promise that resolves with the deserialized account object or null if there was an error.

#### Defined in

[core/hdwallet/api/account.ts:701](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L701)

___

### serialize

▸ **serialize**(): `Promise`<`void`\>

Serializes the account object and encrypts it to 'Browser-local storage'.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:747](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L747)

___

### deserialize

▸ **deserialize**(): `Promise`<[`Account`](Account.md)\>

Deserializes a account object from 'Browser-local storage' by decrypting it and creating a account object in memory.

**`Memberof`**

Account

#### Returns

`Promise`<[`Account`](Account.md)\>

- Returns a Promise that resolves with the deserialized account object or null if there was an error.

#### Defined in

[core/hdwallet/api/account.ts:757](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L757)

___

### saveAccountItselfInfo

▸ **saveAccountItselfInfo**(): `Promise`<`void`\>

Encrypts and stores the account's own information (excluding policy information) to the browser's local storage

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:767](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L767)

___

### getSavedAccountItselfInfo

▸ **getSavedAccountItselfInfo**(): `Promise`<`any`\>

Deserializes a account object (excluding policy information) from 'Browser-local storage' by decrypting it and creating a account object in memory.

**`Memberof`**

Account

#### Returns

`Promise`<`any`\>

- Returns a Promise that resolves with the deserialized account object (excluding policy information) .

#### Defined in

[core/hdwallet/api/account.ts:790](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L790)

___

### removeSavedAccountItselfInfo

▸ **removeSavedAccountItselfInfo**(): `Promise`<`void`\>

Clears the account object (excluding policy information) from the browser's local storage.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:807](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L807)

___

### saveAccountAllStrategyIndexInfo

▸ **saveAccountAllStrategyIndexInfo**(): `Promise`<`void`\>

Serializes all strategy indices of the account to the browser's local storage.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:818](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L818)

___

### getSavedAccountAllStrategyIndexInfo

▸ **getSavedAccountAllStrategyIndexInfo**(): `Promise`<`number`[]\>

Deserializes all strategy indices of the account from the browser's local storage.

**`Memberof`**

Account

#### Returns

`Promise`<`number`[]\>

- An array containing all the strategy indices stored in the browser's local storage.

#### Defined in

[core/hdwallet/api/account.ts:834](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L834)

___

### removeSavedAccountAllStrategyIndexInfo

▸ **removeSavedAccountAllStrategyIndexInfo**(): `Promise`<`void`\>

Clears all strategy indices of the account from the browser's local storage.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:855](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L855)

___

### saveAccountAllStrategyInfo

▸ **saveAccountAllStrategyInfo**(): `Promise`<`void`\>

Serializes all strategy information of the account to the browser's local storage.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:866](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L866)

___

### removeSavedAccountAllStrategyInfo

▸ **removeSavedAccountAllStrategyInfo**(): `Promise`<`void`\>

Clears all strategy information of the account from the browser's local storage.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:883](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L883)

___

### balance

▸ **balance**(): `Promise`<`undefined` \| `string`\>

get the account balance of (bnb/tbnb) from the Ethereum blockchain using web3.

**`Memberof`**

Account

#### Returns

`Promise`<`undefined` \| `string`\>

- A Promise that resolves to the account balance in ether as a string, or undefined if the balance could not be retrieved.

#### Defined in

[core/hdwallet/api/account.ts:899](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L899)

___

### refreshBalance

▸ **refreshBalance**(): `Promise`<`undefined` \| `string`\>

Refreshes the account balance of (bnb/tbnb) from the Ethereum blockchain using web3.
@returns{Promise<string | undefined>} - A Promise that resolves to the account balance in ether as a string, or undefined if the balance could not be retrieved.

**`Memberof`**

Account

#### Returns

`Promise`<`undefined` \| `string`\>

#### Defined in

[core/hdwallet/api/account.ts:909](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L909)

___

### getNLKBalance

▸ **getNLKBalance**(): `Promise`<`undefined` \| `string`\>

get the account balance of nlk from the Ethereum blockchain using web3.

**`Memberof`**

Account

#### Returns

`Promise`<`undefined` \| `string`\>

- A Promise that resolves to the account balance in ether as a string, or undefined if the balance could not be retrieved.

#### Defined in

[core/hdwallet/api/account.ts:940](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L940)

___

### refreshNLKBalance

▸ **refreshNLKBalance**(): `Promise`<`undefined` \| `string`\>

Refreshes the account balance of nlk from the Ethereum blockchain using web3.
@returns{Promise<string | undefined>} - A Promise that resolves to the account balance in ether as a string, or undefined if the balance could not be retrieved.

**`Memberof`**

Account

#### Returns

`Promise`<`undefined` \| `string`\>

#### Defined in

[core/hdwallet/api/account.ts:950](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L950)
