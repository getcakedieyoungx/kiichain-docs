# IBC Precompile

## General Description and Objectives
The IBC precompile enables EVM smart contracts on KiiChain to interact with the Inter-Blockchain Communication (IBC) protocol. This allows contracts to initiate cross-chain token transfers and interact with IBC channels and ports directly from the EVM environment.

**Objectives:**
- Enable seamless cross-chain token transfers from EVM contracts
- Provide access to IBC transfer functionality via precompiled contracts
- Bridge assets and data between KiiChain and other IBC-enabled chains

## Function Calls

### transfer
Initiates an IBC token transfer with full control over timeout and revision parameters.

**Signature:**
```solidity
function transfer(
  string receiver,
  string port,
  string channel,
  string denom,
  uint256 amount,
  uint64 revisionNumber,
  uint64 revisionHeight,
  uint64 timeoutTimestamp,
  string memo
) returns (bool success)
```

**Parameters:**
- `receiver`: Destination address on the target chain
- `port`: IBC port (usually "transfer")
- `channel`: IBC channel ID
- `denom`: Token denomination
- `amount`: Amount to transfer
- `revisionNumber`, `revisionHeight`: Timeout height (for packet expiry)
- `timeoutTimestamp`: Timeout timestamp (for packet expiry)
- `memo`: Optional memo field

### transferWithDefaultTimeout
Initiates an IBC token transfer using default timeout values.

**Signature:**
```solidity
function transferWithDefaultTimeout(
  string receiver,
  string port,
  string channel,
  string denom,
  uint256 amount,
  string memo
) returns (bool success)
```

**Parameters:**
- Same as above, but uses default timeout values for revision and timestamp.

## Queries
Currently, the IBC precompile is focused on transfer functions and does not expose additional query methods via the ABI.

## Events
- `Transfer`: Emitted on successful IBC transfer, includes sender, receiver, denom, port, channel, amount, and timeout info.
