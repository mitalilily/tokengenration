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
burn(uint amount)
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
