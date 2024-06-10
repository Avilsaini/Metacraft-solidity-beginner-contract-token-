
# MyToken

A simple smart contract for minting and burning tokens.

## Description

MyToken is an ERC-20-like smart contract written in Solidity. It allows users to mint new tokens and burn existing tokens. The contract is designed for educational purposes and provides basic functionalities such as tracking balances, total supply, minting, and burning of tokens.

## Getting Started

### Executing program

To run this program, I have  used the remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

On the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension 



```bash

pragma solidity^ 0.8.18;

contract MyToken {

    // Public variables
    string public name = "TOKIN";
    string public symbol = "MTK";
    uint public totalSupply = 0;

    // Mapping from address to balance
    mapping(address => uint) public balances;

    // Mint function to create new tokens
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function to destroy tokens
    function burn (address _address, uint _value) public {
        require(balances[_address] >= _value, "Balance is too low to burn");

        totalSupply -= _value;
        balances[_address] -= _value;
    }
}

```
1. **Compile the contract:**
   \`\`\`bash
   truffle compile
   \`\`\`

2. **Deploy the contract:**
   \`\`\`bash
   truffle migrate
   \`\`\`

3. **Mint tokens:**
   \`\`\`javascript
   const MyToken = artifacts.require("MyToken");

   module.exports = async function (callback) {
     let instance = await MyToken.deployed();
     
     
     callback();
   };
   \`\`\`

4. **Burn tokens:**
   \`\`\`javascript
   const MyToken = artifacts.require("MyToken");

   module.exports = async function (callback) {
     let instance = await MyToken.deployed();
     
     
     callback();
   };
   \`\`\`

 
## Authors

 Avil saini   
avilsaini5309@gmail.com

## License

This project is licensed under the MIT License  

 




 
