[NuLink SDK - v0.5.31](../README.md) / [Modules](../modules.md) / estimateCustomTransactionGas

# Function: estimateCustomTransactionGas

▸ **estimateCustomTransactionGas**(`toAddress`, `rawTxData?`, `value?`, `gasPrice?`, `account?`): `Promise`<``null`` \| `BigNumber`\>

send the raw transaction

**`Throws`**

UnauthorizedError get logined account failed, must be login account first

**`Throws`**

estimateCustomTransactionGas failed exception

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `toAddress` | `string` | The recevier of the transaction, can be empty when deploying a contract. |
| `rawTxData?` | `string` | (Optional) The call data of the transaction, can be empty for simple value transfers. |
| `value?` | `string` | (Optional) The value of the transaction in wei. |
| `gasPrice?` | `string` | (Optional) The gas price set by this transaction, if empty, it will use web3.eth.getGasPrice(). |
| `account?` | [`Account`](../classes/Account.md) | (Optional) The current account information. If the parameter is not passed, the function will call `getWalletDefaultAccount` to retrieve the current account. |

#### Returns

`Promise`<``null`` \| `BigNumber`\>

- Returns the gasFee or null if estimate gas failed .

#### Defined in

[api/pre.ts:1257](https://github.com/NuLink-network/nulink-sdk/blob/f3f9a8b/src/api/pre.ts#L1257)
