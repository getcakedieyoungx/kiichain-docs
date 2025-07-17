# EVM Wasmbinding

## Description
The EVM wasmbinding module allows smart contracts to interact with the EVM module, including making Ethereum calls and querying ERC20 token information.

## Queries

### EthCall
- **Description:** Executes a read-only call to an EVM contract.
- **Request:**  
  ```json
  {
    "eth_call": {
      "contract": "<contract_address>",
      "data": "<call_data>"
    }
  }
  ```
- **Response:**  
  ```json
  {
    "data": "<return_data>"
  }
  ```

### ERC20 Information
- **Description:** Gets ERC20 token metadata (name, symbol, decimals, total supply).
- **Request:**  
  ```json
  {
    "erc20_information": {
      "contract": "<erc20_contract_address>"
    }
  }
  ```
- **Response:**  
  ```json
  {
    "name": "...",
    "symbol": "...",
    "decimals": ...,
    "total_supply": "..."
  }
  ```

### ERC20 Balance
- **Description:** Gets the ERC20 token balance of an address.
- **Request:**  
  ```json
  {
    "erc20_balance": {
      "contract": "<erc20_contract_address>",
      "address": "<user_address>"
    }
  }
  ```
- **Response:**  
  ```json
  {
    "balance": "..."
  }
  ```

### ERC20 Allowance
- **Description:** Gets the allowance of a spender for a given owner.
- **Request:**  
  ```json
  {
    "erc20_allowance": {
      "contract": "<erc20_contract_address>",
      "owner": "<owner_address>",
      "spender": "<spender_address>"
    }
  }
  ```
- **Response:**  
  ```json
  {
    "allowance": "..."
  }
  ```
