# MyToken Solidity Contract

This Solidity program demonstrates a basic token contract called "MyToken" that mimics the creation and management of a token on the Ethereum blockchain. The program includes functionalities for minting and burning tokens, which affect both the total supply and the balance of a specified address.

## Description
The `MyToken` contract is written in Solidity, the programming language used for creating smart contracts on the Ethereum platform. This contract implements key features of a token system:

- **Public Variables**: Stores details such as the token name, token abbreviation, and total supply.
- **Mapping**: Tracks the balance of tokens for each address.
- **Mint Function**: Allows minting (creation) of new tokens by adding to both the total supply and the balance of a specified address.
- **Burn Function**: Reduces the total supply and the balance of a specified address by "burning" tokens, with checks to ensure that the balance is sufficient before burning.

This contract provides a simple but effective demonstration of token creation and destruction mechanisms, often found in more complex token systems such as ERC-20 tokens.

## Getting Started

### Executing the Program

To run this program, you can use Remix, an online Solidity IDE. Follow the steps below to get started.

1. Go to the [Remix website](https://remix.ethereum.org/).
2. Create a new file by clicking on the "+" icon in the left-hand sidebar. Name the file `MyToken.sol`.
3. Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public tokenName = "Ether";
    string public tokenAbbrv = "ETH";
    uint public totalSupply = 0;

    // mapping variable here
    mapping (address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```

### Compiling the Code

1. In Remix, click on the "Solidity Compiler" tab in the left-hand sidebar.
2. Ensure that the compiler version is set to `0.8.18` (or another compatible version).
3. Click the "Compile MyToken.sol" button to compile the contract.

### Deploying the Contract

1. Once the code is compiled, navigate to the "Deploy & Run Transactions" tab in the left-hand sidebar.
2. Select the `MyToken` contract from the dropdown menu.
3. Click the "Deploy" button to deploy the contract to the blockchain.

### Interacting with the Contract

- **Minting Tokens**: After deployment, you can call the `mint` function by providing an address and a token amount. This will increase the total supply and the balance of the specified address.
- **Burning Tokens**: Similarly, the `burn` function can be called with an address and a token amount. If the address has a sufficient balance, the tokens will be deducted from the total supply and the address's balance.

## Authors

**Mitali**  

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details.
