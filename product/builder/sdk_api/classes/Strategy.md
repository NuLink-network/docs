[NuLink SDK - v0.0.6](../README.md) / [Modules](../modules.md) / Strategy

# Class: Strategy

Account class manages policies information, adds policies, deletes policies, and serializes

## Hierarchy

- `IJson`

  ↳ **`Strategy`**

## Table of contents

### Constructors

- [constructor](Strategy.md#constructor)

### Properties

- [accountAddressIndex](Strategy.md#accountaddressindex)
- [addressIndex](Strategy.md#addressindex)
- [id](Strategy.md#id)
- [label](Strategy.md#label)
- [strategyKeyPair](Strategy.md#strategykeypair)

### Methods

- [dump](Strategy.md#dump)
- [load](Strategy.md#load)
- [serialize](Strategy.md#serialize)
- [deserialize](Strategy.md#deserialize)
- [loadSaved](Strategy.md#loadsaved)
- [erase](Strategy.md#erase)

## Constructors

### constructor

• **new Strategy**(`accountAddressIndex`, `strategyAddressIndex`, `label`, `id?`)

Creates a new policy object with the specified account and policy address indices, label, and ID.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `accountAddressIndex` | `number` | `undefined` | The index of the Ethereum account address. |
| `strategyAddressIndex` | `number` | `undefined` | The index of the Ethereum policy address. |
| `label` | `string` | `undefined` | Generate a label name for a local policy. |
| `id?` | `string` | `''` | policy id or generate a policy id if the parameter is not passed. |

#### Overrides

IJson.constructor

#### Defined in

[core/hdwallet/api/account.ts:158](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L158)

## Properties

### accountAddressIndex

• **accountAddressIndex**: `number`

#### Defined in

[core/hdwallet/api/account.ts:145](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L145)

___

### addressIndex

• **addressIndex**: `number`

#### Defined in

[core/hdwallet/api/account.ts:146](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L146)

___

### id

• **id**: `string`

#### Defined in

[core/hdwallet/api/account.ts:147](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L147)

___

### label

• **label**: `string`

#### Defined in

[core/hdwallet/api/account.ts:148](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L148)

___

### strategyKeyPair

• **strategyKeyPair**: `KeyPair`

#### Defined in

[core/hdwallet/api/account.ts:149](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L149)

## Methods

### dump

▸ **dump**(): `string`

Returns a JSON string representation of the account local policy object for encrypted upload files.

**`Memberof`**

Strategy

#### Returns

`string`

- Returns a JSON string representation of the account local policy object for encrypted upload files.

#### Overrides

IJson.dump

#### Defined in

[core/hdwallet/api/account.ts:195](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L195)

___

### load

▸ `Static` **load**(`jsonString`, `_save?`): `Promise`<``null`` \| [`Strategy`](Strategy.md)\>

Loads a policy object from a JSON string.

**`Static`**

**`Memberof`**

Strategy

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `jsonString` | `string` | `undefined` | The JSON string to parse and load. |
| `_save?` | `boolean` | `false` | This parameter is deprecated. Whether to save the loaded object to local storage. |

#### Returns

`Promise`<``null`` \| [`Strategy`](Strategy.md)\>

- Returns a Promise that resolves with the loaded policy object or null if there was an error.

#### Overrides

IJson.load

#### Defined in

[core/hdwallet/api/account.ts:216](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L216)

___

### serialize

▸ **serialize**(): `Promise`<`void`\>

Serializes the policy object and encrypts it to 'Browser-local storage'.

**`Memberof`**

Strategy

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:232](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L232)

___

### deserialize

▸ **deserialize**(): `Promise`<``null`` \| [`Strategy`](Strategy.md)\>

Deserializes a policy object from 'Browser-local storage' by decrypting it and creating a policy object in memory.

**`Memberof`**

Strategy

#### Returns

`Promise`<``null`` \| [`Strategy`](Strategy.md)\>

- Returns a Promise that resolves with the deserialized policy object or null if there was an error.

#### Defined in

[core/hdwallet/api/account.ts:242](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L242)

___

### loadSaved

▸ `Static` **loadSaved**(`accountAddressIndex`, `addressIndex`): `Promise`<``null`` \| [`Strategy`](Strategy.md)\>

Deserializes a policy object from 'Browser-local storage' by decrypting it and creating a policy object in memory.

**`Memberof`**

Strategy

**`Static`**

#### Parameters

| Name | Type |
| :------ | :------ |
| `accountAddressIndex` | `number` |
| `addressIndex` | `number` |

#### Returns

`Promise`<``null`` \| [`Strategy`](Strategy.md)\>

- Returns a Promise that resolves with the deserialized policy object or null if there was an error.

#### Defined in

[core/hdwallet/api/account.ts:270](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L270)

___

### erase

▸ **erase**(): `Promise`<`void`\>

clear a policy object from 'Browser-local storage'

**`Memberof`**

Strategy

**`Static`**

#### Returns

`Promise`<`void`\>

#### Defined in

[core/hdwallet/api/account.ts:285](https://github.com/NuLink-network/nulink-sdk/blob/dec95fc/src/core/hdwallet/api/account.ts#L285)
