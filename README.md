SimpleToken Contract
License
This contract is licensed under the MIT License.

Overview
The SimpleToken contract is a basic implementation of a token contract on the Ethereum blockchain. It allows for the creation, transfer, and management of a token with a fixed total supply.

Features
Token Information
Name: SimpleToken (ST)
Symbol: ST
Total Supply: 1,000,000 tokens
Functions
mint(address to, uint amount)
Allows the contract owner to mint new tokens and assign them to a specific address.
Only the contract owner can call this function.
Emits a Transfer event with the minted amount.
transfer(address to, uint amount)
Allows users to transfer tokens to another address.
Requires the sender to have a sufficient balance.
Emits a Transfer event with the transferred amount.
burn(uint amount)# MyToken Smart Contract

This repository contains the Solidity smart contract `MyToken.sol`, which implements a basic ERC20-like token with minting and burning functionality.

## Contract Overview

The `MyToken` contract allows users to create a token with specific details such as the token name, abbreviation, and total supply. It provides functionality for minting and burning tokens, with appropriate checks to ensure that tokens are only burned if the sender has sufficient balance.

### Contract Details

- **Token Name**: `Ether`
- **Token Abbreviation**: `ETH`
- **Total Supply**: Initialized to `0`

### Features

1. **Public Variables**:  
   - `tokenName`: Stores the name of the token.
   - `tokenAbbrv`: Stores the abbreviation of the token.
   - `totalSupply`: Tracks the total supply of the token.

2. **Balances Mapping**:  
   A mapping of addresses to their respective token balances:
   ```solidity
   mapping (address => uint) public balances;
   ```

3. **Mint Function**:
   - Takes an address and a value as parameters.
   - Increases the total supply of tokens by the specified value.
   - Increases the balance of the provided address by the same value.
   - Example usage:
     ```solidity
     function mint(address _address, uint _value) public {
         totalSupply += _value;
         balances[_address] += _value;
     }
     ```

4. **Burn Function**:
   - Takes an address and a value as parameters.
   - Reduces the total supply of tokens by the specified value if the address has enough balance.
   - Reduces the balance of the provided address by the same value.
   - The function includes a conditional check to ensure that the address has a balance greater than or equal to the value being burned.
   - Example usage:
     ```solidity
     function burn(address _address, uint _value) public {
         if (balances[_address] >= _value) {
             totalSupply -= _value;
             balances[_address] -= _value;
         }
     }
     ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Disclaimer

This contract is a simple educational example and is not intended for production use. Always audit and test smart contracts thoroughly before deploying them on the mainnet.
Allows users to burn (destroy) tokens from their balance.
Requires the sender to have a sufficient balance.
Emits a Transfer event with the burned amount.
Events
Transfer(address indexed from, address indexed to, uint value)
Emitted when tokens are transferred, minted, or burned.
Provides information about the sender, recipient, and amount of tokens involved.
Security
The contract uses a onlyOwner modifier to restrict sensitive functions to the contract owner.
The require statement is used to ensure that users have a sufficient balance before performing token transfers or burns.
Deployment
To deploy this contract, simply compile and deploy it to the Ethereum blockchain using your preferred development environment.

Testing
To test this contract, you can use various testing frameworks and tools, such as Truffle, Hardhat, or Remix.

Contributing
Contributions to this contract are welcome! If you'd like to suggest improvements or report issues, please open a pull request or issue on this repository.

Disclaimer
This contract is provided as-is, and you use it at your own risk. Make sure to thoroughly review and test the code before deploying it to the mainnet.
