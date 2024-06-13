##Token Supply

This is a sample demo code of a mint and burn program using Solidity. The program is used  to show the minting and burning mechanism of the token and supply of the tokens.

##Description

Smart contract: This is implemented in ethereum blockchain using solidity programing language. This contract exposes 4 variables (name, tokenSymbol, totalSupply and balances) as public state variables. There are two other two functions, one called mintTokens and the other is burnTokens mintTokens has 2 parameter address and uint)value. The value will be added to the tokenSupply and the balance of the sender just by calling of mintToken. burnTokens: Transfer addresses and values as parameters to burn and there the if statement which checks if the toknes to be burnt are there with the sender. In the case that the condition is true subtraction will occur to totalSupply as well as the balance.


##Getting Started

##Executing program

You can run this on Remix, an online Solidity IDE.
Step 1: Navigate to https://remix.ethereum.org/

To do this, you will be taken to the newly created file from the left sidebar on the remix website. Save the file with a. sol extension (e.g., MyToken. sol). Paste the following code into the file:

```javascript
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
    string public tokenName = "GOLD";
    string public tokenAbbrv = "GO";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
       totalSupply += _value;
       balances[_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public {
       if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
    }
}

```

Click on Solidity Compiler in the sidebar to compile the code. Select the option "Compiler" with the version of your "0.8.18" (or other compatible version) compiler and click "Compile MyToken sol" button.

After the code is compiled you can link your contract to deploy by going on "Deploy & Run Transactions" in left hand sidebar. Choose the "MyToken" contract from the drop down list and don't forget to click the "Deploy" button.

After you have deployed the contract, you can begin to interact with it. A) Find and click on the "MyToken" contract in the left-hand sidebar, you will find some basic information of the token, such as the abbreviation, name of the token, total supply. It also accept address and token value in mintToken and clicking on it will call mintTokens function and the same will be with the burnTokens.

##Author

Arjun Dhiman

##License

This MyToken is licensed under the MIT License# JAVASCRIPT-ASSESSMENT-2
