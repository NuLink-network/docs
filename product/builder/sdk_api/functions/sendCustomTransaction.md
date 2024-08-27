[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / sendCustomTransaction

# Function: sendCustomTransaction

▸ **sendCustomTransaction**(`toAddress`, `rawTxData?`, `value?`, `gasPrice?`, `gasLimit?`, `account?`): `Promise`<``null`` \| `string`\>

send the raw transaction

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

**`Throws`**

set Transaction failed exception

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `toAddress` | `string` | The recevier of the transaction, can be empty when deploying a contract. |
| `rawTxData?` | `string` | (Optional) The call data of the transaction, can be empty for simple value transfers. |
| `value?` | `string` | (Optional) The value of the transaction in wei. |
| `gasPrice?` | `string` | (Optional) The gas price set by this transaction, if empty, it will use web3.eth.getGasPrice(). |
| `gasLimit?` | `BigNumber` | (Optional) set gas limit |
| `account?` | [`Account`](../classes/Account.md) | (Optional) The current account information. If the parameter is not passed, the function will call `getWalletDefaultAccount` to retrieve the current account. |

#### Returns

`Promise`<``null`` \| `string`\>

- Returns the transactionHash.

#### Defined in

[api/pre.ts:1202](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L1202)
