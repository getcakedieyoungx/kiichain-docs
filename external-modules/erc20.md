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

## Reference
- [cosmos/evm ERC20 implementation](https://github.com/cosmos/evm/tree/main/x/erc20)
- [Ethereum ERC20 standard](https://eips.ethereum.org/EIPS/eip-20) 
