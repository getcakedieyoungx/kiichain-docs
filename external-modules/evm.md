# EVM Module

## General Description and Objectives
The EVM module integrates the Ethereum Virtual Machine into KiiChain, enabling the execution of Ethereum-compatible smart contracts and dApps. It allows developers to deploy and interact with Solidity contracts, use Ethereum tools, and benefit from the security and interoperability of the Cosmos ecosystem.

**Objectives:**
- Provide full EVM compatibility for smart contract deployment and execution
- Enable Ethereum dApp migration and interoperability
- Support Ethereum tooling (Metamask, Remix, Hardhat, etc.)

## Main Function Calls
- Deploy and execute Solidity smart contracts
- Interact with contracts using standard Ethereum transactions
- Support for contract events, logs, and Ethereum JSON-RPC methods

## Queries
- Query contract state and storage
- Access Ethereum account balances and nonces
- Retrieve transaction receipts and logs

## Usage Examples

### Deploying a Smart Contract
You can deploy a Solidity contract using tools like Hardhat or Remix. Example (using web3.js):

```javascript
const contract = new web3.eth.Contract(abi);
const deployTx = contract.deploy({ data: bytecode });
const receipt = await deployTx.send({ from: "0xYourAddress", gas: 3000000 });
console.log("Contract deployed at:", receipt.options.address);
```

### Interacting with a Contract
Call a contract function:

```javascript
const result = await contract.methods.myFunction(arg1, arg2).call();
console.log(result);
```

Send a transaction to a contract:

```javascript
await contract.methods.myFunction(arg1, arg2).send({ from: "0xYourAddress" });
```

## Reference
- [cosmos/evm GitHub repository](https://github.com/cosmos/evm)
- [KiiChain EVM integration](https://github.com/KiiChain/kiichain/tree/main/x/vm) 
