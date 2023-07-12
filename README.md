MyToken Contract

This smart contract was created using the programming language Solidity, which is used to develop Ethereum-based smart contracts. A fundamental ERC-20 token named "MyToken" with the symbol "RUSS" is defined in the contract. The contract permits the creation and burning of tokens as well as checking token balances.

Prerequisites
This code requires Solidity version 0.8.18 or a compatible version to compile and deploy.

Contract Overview
The MyToken contract is defined as follows:

solidity
Copy code
pragma solidity 0.8.18;

contract MyToken {
    // Public variables
    string public tokenName = "RUSSRUSS";
    string public tokenAbbrv = "RUSS";
    uint public totalsupply = 0;

    // Mapping variable
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalsupply += _value; 
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value){
            totalsupply -= _value;
            balances[_address] -= _value;
        }
    }
}
Contract Details
The contract consists of the following components:
Public Variables
tokenName (string): Represents the name of the token. In this case, it is set to "RUSSRUSS".
tokenAbbrv (string): Represents the abbreviated symbol of the token. In this case, it is set to "RUSS".
totalsupply (uint): Represents the total supply of tokens. Initially set to 0.

Mapping Variable
balances (mapping): This mapping associates Ethereum addresses with their respective token balances. It allows users to query the balance of a specific address using the balances[_address] syntax.

Mint Function
The mint function is used to create new tokens and assign them to a specified address. It takes two parameters:
_address (address): The address to which the newly created tokens will be assigned.
_value (uint): The number of tokens to be created and assigned
Inside the mint function, the total supply is increased by the _value amount, and the _value tokens are added to the balance of the _address.

Burn Function
The burn function is used to remove tokens from a specified address. It takes two parameters:
_address (address): The address from which tokens will be burned.
_value (uint): The number of tokens to be burned.
Inside the burn function, it first checks if the balance of the _address is greater than or equal to the _value. If it is, the total supply is decreased by the _value amount, and the _value tokens are subtracted from the balance of the _address.

Usage
Deploy the MyToken contract using a Solidity compiler that works with the Ethereum network.
You can talk to the contract after it has been deployed by calling the mint and burn functions.
Call the mint function, indicate the address to which the tokens should be assigned, and the required quantity of tokens to be created.
To remove tokens, call the burn function and provide the address and number of tokens that should be burned.
