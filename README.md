# Project Title

Creating a Token using Solidity

## Description

* In a contract named MyToken,there will be public variables that store the details about our coin (Token Name, Token Abbrv., Total Supply).
* Our contract will have a mapping of addresses to balances (address => uint).
* We will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount.
* Our contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the address.
* Lastly, our burn function should have conditionals to make sure the balance of account is greater than or equal to the amount that is supposed to be burned.

## Getting Started


### Language used

* Solidity
### IDE used


* Remix IDE
### Executing program

# * How to run the program
* Just simply run the following code on Remix IDE.
* Then after compilation is done, deploy the smart contract. Simply put the values of mint and burn functions (i.e. address and values)
* Transact the functions and check balance if the code is being properly deployed.



```

//SPDX-License-Identifier: MIT
pragma solidity 0.8.26;
/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public Name = "DODO";
    string public Abbreviation = "DD";
    uint public TotalSupply = 0;

    // mapping variable here
    mapping(address => uint) public Balance;

    // mint function
    function mint (address Address, uint Value) public{
        TotalSupply += Value;
        Balance[Address] += Value;
    }

    // burn function
     function burn (address Address, uint Value) public{
         if (Balance[Address] >= Value){
        TotalSupply -= Value;
        Balance[Address] -= Value;
    }
     }
}code blocks for commands
```


## Authors

Contributors names and contact info

Swastika Thakur 

https://github.com/sw4stikaa

## License

This project is licensed under the MIT License.
