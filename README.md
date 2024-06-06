MyToken Contract

Code:

    // SPDX-License-Identifier: MIT
    pragma solidity 0.8.18;
    contract MyToken {

    // Public variables
    string public tokenName = "MyToken";
    string public tokenAbbrv = "MTK";
    uint256 public totalSupply = 0;
    
    // Mapping from address to balance
    mapping(address => uint256) public balances;

    // Mint function
    function mint(address _address, uint256 _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function using if-else
    function burn(address _address, uint256 _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        } else {
            // Handle the case where balance is insufficient
            revert("Insufficient balance to burn");
        }
    }
    }

Explanation:

Public Variables:
'tokenName' stores the name of the token and is public in nature.
'tokenAbbrv' stores the abbreviation of the token and is public in nature.
'totalSupply' stores the total supply of the token and is public in nature.

Mapping:
'balances' maps addresses to their respective token balances.

Mint Function:
This function increases the total supply of tokens and the balance of the specified address by the given value.

Burn Function (with if-else):
The burn function first checks if the address has a sufficient balance to burn the specified amount of tokens using an if statement.
If the condition is met, it decreases the total supply and the balance of the specified address.
If the balance is insufficient, it uses revert to stop the execution and provide an error message.

This is brief explanation of the provided code.

AUTHOR:
Arju Kumari
