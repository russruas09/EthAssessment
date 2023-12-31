MyToken Contract

This Solidity contract implements a basic token called MyToken, with the functionality of minting and burning tokens.The contract is implemented in Solidity, a programming language used for writing smart contracts on the Ethereum blockchain.


Requirements

The following conditions are intended to be satisfied by the MyToken contract:


Public variables in the contract should be used to record information about the coin, such as the token name, token abbreviation, and the total supply.

There should be a mapping in the contract that links addresses to token balances.

A mint feature that raises the total quantity of tokens and boosts the balance at the "sender" address should be included in the contract.

A burn function that reduces the overall supply of tokens and subtracts the specified sum from the balance of the "sender" address should be included in the contract.

To guarantee that the balance of the "sender" is more than or equal to the amount to be burned, the burn function should have conditionals.

Code

solidity


    // SPDX-License-Identifier: MIT
    pragma solidity 0.8.18;

    contract MyToken {

    // public variables here
    string public tokenName = "RUSSRUSS";
    string public tokenAbbrv = "RUSS";
    uint public totalSupply = 0;

    // mapping variable here
    mapping (address => uint) public balances;
    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances [_address] += _value;    
    }
    // burn function
    function burn (address _address, uint _value) public {
        if (balances[_address] >= _value){
        totalSupply -= _value;
        balances [_address] -= _value;  
            }   
        }
    }


Public Variables

The following public variables are defined in the contract:

tokenName: A string representing the name of the token (e.g., "RUSSRUSS").

tokenAbbrv: A string representing the abbreviated name of the token (e.g., "RUSS").

totalSupply: An unsigned integer representing the total supply of the token. Initially set to 0.



Mapping

The contract uses a mapping variable named balances to keep track of token balances for each address. The mapping maps an address to an unsigned integer representing the balance of tokens owned by that address.



Mint Function

The mint function allows the creation of new tokens and assigns them to a specified address. It takes two parameters: _address (the recipient address) and _value (the amount of tokens to be minted). The function increases the total supply of tokens by the specified value and adds the minted tokens to the balance of the specified address.



Burn Function

The burn function allows the destruction of tokens owned by a specified address. It takes two parameters: _address (the address owning the tokens) and _value (the amount of tokens to be burned). The function checks if the balance of the specified address is greater than or equal to the value to be burned. If so, it decreases the total supply by the specified value and reduces the balance of the specified address by the burned tokens.



License

This contract is released under the MIT License.
