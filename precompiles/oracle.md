# Oracle Precompile

## General Description and Objectives
The Oracle precompile allows EVM smart contracts on KiiChain to access on-chain price oracles. Contracts can query exchange rates, all available rates, and time-weighted average prices (TWAPs) for supported assets.

**Objectives:**
- Provide EVM contracts with access to real-time price data
- Enable DeFi and other applications to use on-chain oracles for asset pricing and analytics

## Function Calls / Queries

### getExchangeRate
Returns the current exchange rate for a given denom.

**Signature:**
```solidity
function getExchangeRate(string denom) view returns (string rate, string lastUpdate, int64 lastUpdateTimestamp)
```

**Parameters:**
- `denom`: The asset denomination (e.g., "uusd", "ukii")

**Returns:**
- `rate`: The current exchange rate
- `lastUpdate`: Last update time (string)
- `lastUpdateTimestamp`: Last update time (timestamp)

---

### getExchangeRates
Returns all available exchange rates.

**Signature:**
```solidity
function getExchangeRates() view returns (string[] denoms, string[] rates, string[] lastUpdate, uint256[] lastUpdateTimestamps)
```

**Returns:**
- `denoms`: List of asset denoms
- `rates`: List of rates
- `lastUpdate`: List of last update times
- `lastUpdateTimestamps`: List of last update timestamps

---

### getTwaps
Returns time-weighted average prices for a lookback period (in seconds).

**Signature:**
```solidity
function getTwaps(uint256 lookbackSeconds) view returns (string[] denoms, string[] twaps)
```

**Parameters:**
- `lookbackSeconds`: Number of seconds to look back for TWAP calculation

**Returns:**
- `denoms`: List of asset denoms
- `twaps`: List of TWAP values
