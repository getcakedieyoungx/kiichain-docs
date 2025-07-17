# Bech32 Wasmbinding

## Description
The Bech32 wasmbinding module provides conversion utilities between Ethereum hex addresses and Cosmos Bech32 addresses. This is useful for smart contracts and dApps that need to interoperate between EVM and Cosmos address formats.

## Queries

### Hex to Bech32
- **Description:** Converts an Ethereum hex address to a Cosmos Bech32 address with a given prefix.
- **Request:**  
  ```json
  {
    "hex_to_bech32": {
      "address": "<hex_address>",
      "prefix": "<bech32_prefix>"
    }
  }
  ```
- **Response:**  
  ```json
  {
    "address": "<bech32_address>"
  }
  ```

### Bech32 to Hex
- **Description:** Converts a Cosmos Bech32 address to an Ethereum hex address.
- **Request:**  
  ```json
  {
    "bech32_to_hex": {
      "address": "<bech32_address>"
    }
  }
  ```
- **Response:**  
  ```json
  {
    "address": "<hex_address>"
  }
  ```
