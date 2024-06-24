# Project: Create a Token

In this Solidity project, the task involves creating a contract using the Remix environment. The goal is to establish a basic token that can facilitate minting and burning operations. Minting will result in the expansion of the total supply and the balance of a specified address, whereas burning will lead to a reduction in the total supply and the balance of a designated address, as long as the address possesses adequate tokens to burn.

## Description

This program shows how to create a token written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. 

## Getting Started
There are no installations required. Only the web browser is needed, and it is ideal to use Remix. Remix website at: https://remix.ethereum.org/.

### Executing program
1. Create a new file by clicking on the "+" icon in the sidebar. _(Remix website)_
2. Name the file and use the .sol file extension
3. Copy and paste the code shown below (which can also be seen in myToken.sol from this repository)
   ```
    // SPDX-License-Identifier: MIT
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

contract MyToken {

    // public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

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
  6. Compile the code by clicking on the Solidity compiler icon in the sidebar.
  7. Then, click "Deploy & Run Transactions" icon found on the sidebar.
  8. To deploy, click on the orange "Deploy" button.
  9. Configure and test by following the conditions stated in the requirements comment at the code's beginning.

## Authors
Vashti Leonie D. Bauson
