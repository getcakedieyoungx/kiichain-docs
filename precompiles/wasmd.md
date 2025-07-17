# Wasmd Precompile

## General Description and Objectives
The Wasmd precompile enables EVM smart contracts on KiiChain to interact with CosmWasm contracts. This allows EVM contracts to instantiate, execute, and query CosmWasm smart contracts directly.

**Objectives:**
- Bridge EVM and CosmWasm contract ecosystems
- Allow EVM contracts to deploy and interact with CosmWasm contracts
- Enable hybrid dApps leveraging both EVM and CosmWasm features

## Function Calls

### instantiate
Instantiates a new CosmWasm contract.

**Signature:**
```solidity
function instantiate(
  address admin,
  uint64 codeID,
  string label,
  bytes msg,
  tuple(string denom, uint256 amount)[] coins
) returns (bool success)
```

**Parameters:**
- `admin`: Admin address for the new contract
- `codeID`: Code ID of the contract to instantiate
- `label`: Human-readable label for the contract
- `msg`: Initialization message (as bytes)
- `coins`: List of coins to send with instantiation

---

### execute
Executes a message on a CosmWasm contract.

**Signature:**
```solidity
function execute(
  string contractAddress,
  bytes msg,
  tuple(string denom, uint256 amount)[] coins
) returns (bool success)
```

**Parameters:**
- `contractAddress`: Address of the CosmWasm contract
- `msg`: Execution message (as bytes)
- `coins`: List of coins to send with execution

## Queries

### queryRaw
Performs a raw query on a CosmWasm contract.

**Signature:**
```solidity
function queryRaw(string contractAddress, bytes queryData) view returns (bytes data)
```

**Parameters:**
- `contractAddress`: Address of the CosmWasm contract
- `queryData`: Raw query data (as bytes)

---

### querySmart
Performs a smart query on a CosmWasm contract.

**Signature:**
```solidity
function querySmart(string contractAddress, bytes msg) view returns (bytes data)
```

**Parameters:**
- `contractAddress`: Address of the CosmWasm contract
- `msg`: Query message (as bytes)

## Events
- `ContractInstantiated`: Emitted when a contract is instantiated
- `ContractExecuted`: Emitted when a contract is executed
