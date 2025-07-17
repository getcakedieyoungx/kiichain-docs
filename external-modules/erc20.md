# ERC20 Module

## General Description and Objectives
The ERC20 module provides support for ERC20 token standards within the EVM environment on KiiChain. It enables the creation, management, and interoperability of fungible tokens, allowing seamless integration with Ethereum-based DeFi protocols and wallets.

**Objectives:**
- Enable ERC20 token creation and management on KiiChain
- Support standard ERC20 functions for compatibility with Ethereum dApps
- Facilitate token transfers, approvals, and DeFi integrations

## Main Function Calls
- `totalSupply()`: Returns the total token supply
- `balanceOf(address account)`: Returns the balance of a specific account
- `transfer(address to, uint256 amount)`: Transfers tokens to another address
- `approve(address spender, uint256 amount)`: Approves another address to spend tokens
- `transferFrom(address from, address to, uint256 amount)`: Transfers tokens on behalf of another address
- `allowance(address owner, address spender)`: Returns the remaining number of tokens that spender can spend

## Queries
- Query token balances, allowances, and total supply
- Retrieve token metadata (name, symbol, decimals)

## Usage Examples

### Querying Token Balance
```javascript
const balance = await erc20Contract.methods.balanceOf("0xYourAddress").call();
console.log("Your balance:", balance);
```

### Transferring Tokens
```javascript
await erc20Contract.methods.transfer("0xRecipientAddress", 1000).send({ from: "0xYourAddress" });
```

### Approving and Transferring From
```javascript
await erc20Contract.methods.approve("0xSpenderAddress", 500).send({ from: "0xYourAddress" });
await erc20Contract.methods.transferFrom("0xYourAddress", "0xRecipientAddress", 500).send({ from: "0xSpenderAddress" });
```

### Checking Allowance
```javascript
const allowance = await erc20Contract.methods.allowance("0xYourAddress", "0xSpenderAddress").call();
console.log("Allowance:", allowance);
```

## Reference
- [cosmos/evm ERC20 implementation](https://github.com/cosmos/evm/tree/main/x/erc20)
- [Ethereum ERC20 standard](https://eips.ethereum.org/EIPS/eip-20) 
