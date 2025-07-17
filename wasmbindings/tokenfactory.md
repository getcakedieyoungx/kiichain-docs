# TokenFactory Wasmbinding

## Description
The TokenFactory wasmbinding module allows smart contracts to create, mint, burn, and manage custom tokens, as well as query token metadata and parameters.

## Tx (Messages)

- **CreateDenom:** Create a new token denom.
- **MintTokens:** Mint tokens to an address.
- **BurnTokens:** Burn tokens from an address.
- **ChangeAdmin:** Change the admin of a denom.
- **SetMetadata:** Set metadata for a denom.
- **ForceTransfer:** Force transfer tokens between addresses.

## Queries

### FullDenom
- **Description:** Get the full denom for a creator and subdenom.
- **Request:**  
  ```json
  {
    "full_denom": {
      "creator_addr": "<creator_address>",
      "subdenom": "<subdenom>"
    }
  }
  ```
- **Response:**  
  ```json
  {
    "denom": "<full_denom>"
  }
  ```

### Admin
- **Description:** Get the admin address for a denom.
- **Request:**  
  ```json
  {
    "admin": {
      "denom": "<denom>"
    }
  }
  ```
- **Response:**  
  ```json
  {
    "admin": "<admin_address>"
  }
  ```

### Metadata
- **Description:** Get metadata for a denom.
- **Request:**  
  ```json
  {
    "metadata": {
      "denom": "<denom>"
    }
  }
  ```
- **Response:**  
  ```json
  {
    "metadata": { ... }
  }
  ```

### DenomsByCreator
- **Description:** Get all denoms created by a specific address.
- **Request:**  
  ```json
  {
    "denoms_by_creator": {
      "creator": "<creator_address>"
    }
  }
  ```
- **Response:**  
  ```json
  {
    "denoms": [ ... ]
  }
  ```

### Params
- **Description:** Get token factory module parameters.
- **Request:**  
  ```json
  {
    "params": {}
  }
  ```
- **Response:**  
  ```json
  {
    "params": { ... }
  }
  ``` 
