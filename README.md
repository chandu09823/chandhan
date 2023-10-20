# MyToken Smart Contract

This is a simple Solidity smart contract named `MyToken` that allows for minting and burning of a custom token. 

## Description

This contract facilitates the creation of a custom token named "Chandhan M" with the abbreviation "CM". It includes functions to mint and burn tokens for specified addresses.

```javascript

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    string public Name = "Chandhan M";
    string public Abbreviation = "CM";
    uint256 public totalAmount = 800;

    mapping(address => uint256) public balances;


    function mint(address account, uint256 value) public {
        require(account != address(0), "Invalid address");
        totalAmount += value;
        balances[account] += value;
    }

    function burn(address account, uint256 value) public {
        require(balances[account] >= value, "Insufficient balance");
        totalAmount -= value;
        balances[account] -= value;
    }
}
``` 
## Functions

1. `mint`: This function mints a specified amount of tokens for a given address.

2. `burn`: This function burns a specified amount of tokens from a given address.

## Usage

The contract can be utilized to create and manage a custom token on the Ethereum blockchain. It allows for the minting and burning of tokens, enabling control over the token supply.

## Security

- Ensure to review and verify the code thoroughly for any potential security vulnerabilities.
- Consider implementing additional security measures if deploying on the mainnet or a production environment.

## How to Compile and Deploy

1. **Compilation:** 
   - Go to the "Solidity Compiler" section in the left sidebar.
   - Select the appropriate version, such as "0.8.18," from the "Compiler" option.
   - Click the "Compile token.sol" button to compile the code.

2. **Deployment:**
   - Move to the "Deploy & Run Transactions" tab on the left sidebar.
   - Choose the "mytoken" contract from the dropdown menu.
   - Click the "Deploy" button to deploy the contract.

3. **Interaction:**
   - Execute the "burn" or "mint" functions under the "token" contract in the left sidebar.
   - Provide the necessary parameters for the function you wish to execute.
   - Monitor the total balance by selecting the "totalamount" option.

Ensure you thoroughly test the contract before deploying it to the mainnet or any production environment.

## Author
Chandhan M

chandua0514@gmail.com

*This smart contract is provided under the MIT License.*
