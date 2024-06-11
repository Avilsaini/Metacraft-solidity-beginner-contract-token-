
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
### Steps to Implement the Contract

1. **Define Public Variables**:
   - The contract already defines public variables `name`, `nickname`, and `supply` to store details about the token.

2. **Define Mapping**:
   - The contract includes a mapping named `userBalances` to map addresses to their token balances.

3. **Implement Mint Function**:
   - The `mint` function increases the `supply` and updates the balance of the specified address (`_address`).

4. **Implement Burn Function**:
   - The `burn` function decreases the `supply` and the balance of the specified address (`_address`).
   - It ensures that the balance is sufficient before burning tokens using a `require` statement.;
   \`\`\`


### Contract Requirements


1. ****Public Variables****: The contract will have public variables to store the details about the token, including:
   - Token Name
   - Token symbol (Abbrv.)
   - Total Supply

2. ****Mapping of Addresses to Balances****: A mapping will be used to keep track of the balances of different addresses.

3. ****Mint Function****: A function to mint new tokens. This function will:
   - Take an address and a value as parameters.
   - Increase the total supply by the specified value.
   - Increase the balance of the specified address by the same amount.

4. ****Burn Function****: A function to burn tokens. This function will:
   - Take an address and a value as parameters.
   - Decrease the total supply by the specified value.
   - Decrease the balance of the specified address by the same amount.
   - Ensure that the balance of the address is greater than or equal to the amount to be burned before proceeding.
 
## Authors

 Avil saini   
avilsaini5309@gmail.com

## License

This project is licensed under the MIT License  

 




 
