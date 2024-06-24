# Project Title

Understanding the basic functionality of Smart Contract and solidity language.

## Description

A contract consists of token name , abbrivation and many other things. Here we have use mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount and the burn function which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the address.
## Getting Started

### Installing

* On Remix online ide
### Executing program
To run this program, you can use Remix, an online Solidity IDE.
```
pragma solidity 0.8.18;

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

contract token {



    // public variables here
    string public token_name = "IGNITE";
    string public token_abbrv  = "IGN";
    uint public total_supply = 0;


    // mapping variable here
     mapping(address => uint ) public balances;

    // mint function
    function mint (address _address , uint _value) public {
      total_supply += _value;
      balances [_address] += _value;
    }

    // burn function
    function burn (address _address , uint _value) public {
      if (balances[_address] >= _value ){
         total_supply -= _value;
         balances [_address] -= _value;
      }
      }
}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "mytoken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "my token" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn function.


## Authors
[@saransh15151](https://github.com/saransh15151)
## License

This project is licensed under the MIT License - see the LICENSE.md file for details
