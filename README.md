# Project: Create a Token

In this Solidity project, the task involves creating a contract using the Remix environment. The goal is to establish a basic token that can facilitate minting and burning operations. Minting will result in the expansion of the total supply and the balance of a specified address, whereas burning will lead to a reduction in the total supply and the balance of a designated address, as long as the address possesses adequate tokens to burn.

## Description

This program shows how to create a token written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. 

## Getting Started
There are no installations required. Only the web browser is needed, and it is ideal to use Remix. Remix website at: https://remix.ethereum.org/.

### Executing program
1. **Create a New File**
   - In Remix, click on the "+" icon in the sidebar to create a new file.
   - Name the file with a `.sol` extension (e.g., `MyToken.sol`).

2. **Copy and Paste the Code**
   - Copy the Solidity code provided below and paste it into your newly created `.sol` file.
   ```
    // SPDX-License-Identifier: MIT
   pragma solidity 0.8.18;
   */
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

3. **Compile the Code**
      - Click on the "Solidity compiler" icon in the sidebar.
      - Select the appropriate compiler version (0.8.18) and click on the "Compile MyToken.sol" button.
        
4. **Deploy the Contract**
      - Click on the "Deploy & Run Transactions" icon in the sidebar.
      - Ensure the correct environment is selected (e.g., JavaScript VM).
      - Click on the "Deploy" button.
5. **Interact with the Contract**
      - After deployment, the contract will appear under the "Deployed Contracts" section.
      - You can now interact with the contract's functions (mint and burn) using the provided UI.

   
## Authors
Vashti Leonie D. Bauson

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
