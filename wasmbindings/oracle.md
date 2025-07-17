# Oracle Wasmbinding

## Description
The Oracle wasmbinding module allows smart contracts to query price oracles for exchange rates, all rates, and time-weighted average prices (TWAPs).

## Queries

### Exchange Rate
- **Description:** Gets the exchange rate for a specific denom.
- **Request:**  
  ```json
  {
    "exchange_rate": {
      "denom": "<denom>"
    }
  }
  ```
- **Response:**  
  ```json
  {
    "exchange_rate": "..."
  }
  ```

### Exchange Rates
- **Description:** Gets all available exchange rates.
- **Request:**  
  ```json
  {
    "exchange_rates": {}
  }
  ```
- **Response:**  
  ```json
  {
    "exchange_rates": [
      {"denom": "...", "exchange_rate": "..."},
      ...
    ]
  }
  ```

### TWAPs
- **Description:** Gets time-weighted average prices for a lookback period.
- **Request:**  
  ```json
  {
    "twaps": {
      "lookback_seconds": <seconds>
    }
  }
  ```
- **Response:**  
  ```json
  {
    "twaps": [
      {"denom": "...", "twap": "..."},
      ...
    ]
  }
  ``` 
