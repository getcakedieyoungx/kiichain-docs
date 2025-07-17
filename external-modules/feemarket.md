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

## Reference
- [cosmos/evm FeeMarket implementation](https://github.com/cosmos/evm/tree/main/x/feemarket)
- [EIP-1559 specification](https://eips.ethereum.org/EIPS/eip-1559) 
