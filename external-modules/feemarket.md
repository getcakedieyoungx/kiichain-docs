# FeeMarket Module

## General Description and Objectives
The FeeMarket module implements Ethereum's EIP-1559 fee market mechanism on KiiChain. It manages base fees, priority fees (tips), and block gas limits, providing a predictable and efficient fee structure for EVM transactions.

**Objectives:**
- Enable EIP-1559 style dynamic fee market for EVM transactions
- Improve transaction inclusion predictability and user experience
- Support base fee, max fee, and priority fee (tip) parameters

## Main Function Calls
- Set and update base fee per gas
- Calculate max fee and priority fee for transactions
- Adjust block gas limits dynamically

## Queries
- Query current base fee, gas usage, and block gas limits
- Retrieve fee market parameters and configuration

## Usage Examples

### Querying the Current Base Fee and Gas Limit
You can use the Ethereum JSON-RPC API to get the current base fee and gas limit:

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockByNumber",
  "params": ["latest", false],
  "id": 1
}
```

The response will include `baseFeePerGas` and `gasLimit` fields.

---

### Sending an EIP-1559 Transaction
When sending a transaction, specify `maxFeePerGas` and `maxPriorityFeePerGas`:

```javascript
const tx = {
  from: "0xYourAddress",
  to: "0xRecipientAddress",
  value: "0x2386f26fc10000", // 0.01 ETH
  gas: 21000,
  maxFeePerGas: "0x59682f00",      // e.g., 1.5 Gwei
  maxPriorityFeePerGas: "0x3b9aca00" // e.g., 1 Gwei
};

await web3.eth.sendTransaction(tx);
```

- `maxFeePerGas`: The maximum fee the user is willing to pay
- `maxPriorityFeePerGas`: The tip for the validator

## Reference
- [cosmos/evm FeeMarket implementation](https://github.com/cosmos/evm/tree/main/x/feemarket)
- [EIP-1559 specification](https://eips.ethereum.org/EIPS/eip-1559) 
