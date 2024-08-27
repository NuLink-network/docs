[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / Account

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

[core/hdwallet/api/account.ts:323](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L323)

## Properties

### name

• **name**: `string` = `''`

#### Defined in

[core/hdwallet/api/account.ts:308](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L308)

___

### address

• **address**: `string` = `''`

#### Defined in

[core/hdwallet/api/account.ts:309](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L309)

___

### addressIndex

• **addressIndex**: `number` = `-1`

#### Defined in

[core/hdwallet/api/account.ts:310](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L310)

___

### id

• **id**: `string` = `''`

#### Defined in

[core/hdwallet/api/account.ts:311](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L311)

___

### encryptedKeyPair

• **encryptedKeyPair**: `KeyPair`

#### Defined in

[core/hdwallet/api/account.ts:312](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L312)

___

### verifyKeyPair

• **verifyKeyPair**: `KeyPair`

#### Defined in

[core/hdwallet/api/account.ts:313](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L313)

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

[core/hdwallet/api/account.ts:356](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L356)

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

[core/hdwallet/api/account.ts:415](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L415)

___

### createStrategyByLabel

▸ **createStrategyByLabel**(`label`): `Promise`<[`Strategy`](Strategy.md)\>

Creates a new policy object with the specified label and a generated ID. The policy object is used to encrypt data/files uploaded by the user.

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

[core/hdwallet/api/account.ts:434](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L434)

___

### createStrategy

▸ **createStrategy**(`label`, `id?`): `Promise`<[`Strategy`](Strategy.md)\>

Creates a new policy object with the specified label and ID, and adds it to the policy mapping. The policy object is used to encrypt data/files uploaded by the user.

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

[core/hdwallet/api/account.ts:457](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L457)

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

[core/hdwallet/api/account.ts:480](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L480)

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

[core/hdwallet/api/account.ts:510](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L510)

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

[core/hdwallet/api/account.ts:522](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L522)

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

[core/hdwallet/api/account.ts:535](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L535)

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

[core/hdwallet/api/account.ts:552](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L552)

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

[core/hdwallet/api/account.ts:562](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L562)

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

[core/hdwallet/api/account.ts:579](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L579)

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

[core/hdwallet/api/account.ts:596](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L596)

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

[core/hdwallet/api/account.ts:649](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L649)

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

[core/hdwallet/api/account.ts:692](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L692)

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

[core/hdwallet/api/account.ts:725](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L725)

___

### serialize

▸ **serialize**(): `Promise`<`void`\>

Serializes the account object and encrypts it to 'Browser-local storage'.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:771](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L771)

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

[core/hdwallet/api/account.ts:781](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L781)

___

### saveAccountItselfInfo

▸ **saveAccountItselfInfo**(): `Promise`<`void`\>

Encrypts and stores the account's own information (excluding policy information) to the browser's local storage

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:791](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L791)

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

[core/hdwallet/api/account.ts:814](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L814)

___

### removeSavedAccountItselfInfo

▸ **removeSavedAccountItselfInfo**(): `Promise`<`void`\>

Clears the account object (excluding policy information) from the browser's local storage.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:831](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L831)

___

### saveAccountAllStrategyIndexInfo

▸ **saveAccountAllStrategyIndexInfo**(): `Promise`<`void`\>

Serializes all strategy indices of the account to the browser's local storage.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:842](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L842)

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

[core/hdwallet/api/account.ts:858](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L858)

___

### removeSavedAccountAllStrategyIndexInfo

▸ **removeSavedAccountAllStrategyIndexInfo**(): `Promise`<`void`\>

Clears all strategy indices of the account from the browser's local storage.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:879](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L879)

___

### saveAccountAllStrategyInfo

▸ **saveAccountAllStrategyInfo**(): `Promise`<`void`\>

Serializes all strategy information of the account to the browser's local storage.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:890](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L890)

___

### removeSavedAccountAllStrategyInfo

▸ **removeSavedAccountAllStrategyInfo**(): `Promise`<`void`\>

Clears all strategy information of the account from the browser's local storage.

**`Memberof`**

Account

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:907](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L907)

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

[core/hdwallet/api/account.ts:923](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L923)

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

[core/hdwallet/api/account.ts:933](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L933)

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

[core/hdwallet/api/account.ts:964](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L964)

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

[core/hdwallet/api/account.ts:974](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/core/hdwallet/api/account.ts#L974)
