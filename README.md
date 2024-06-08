# TOKEN CONTRACT

This Solidity program is a contract that creates an Token and sent to users/addresses. This is my Metacrafters ETH Beginner Final Project of metacraft.
## Description

This program is a smart contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has three state variable that is used to store details about the coin(i.e token name,token abbrviation and total supply),also it have two functions, i.e. Mint, Burn function. By using the mint function we can add more tokens to the total supply and to the balance and send tokens to address and by using the burn function we can remove the tokens from total supply and also remove it from the balance. I have also added a check measure where if the current balance of the user is less than the amount that is entered to be burned the transaction will fail.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., ethproject.sol). Copy and paste the following code into the file:

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
    string public token_name="Aman";
    string public token_abbrv="AMN";
    uint public total_supply;

    // mapping variable here
    mapping(address=>uint) public balances;

    // mint function
    function mint(address _address,uint _value) public
    {
        total_supply += _value;
        balances[_address]+= _value;
    }

    // burn function
    function burn(address _address,uint _value) public
    {
        if(balances[_address]>=_value)
        {
            total_supply -= _value;
            balances[_address]-= _value;
        }
      
    }
}

```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile ethproject.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the available functions. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "totalSupply" function to see the total supply of the token. Execute different functions and try out the contract.

## Authors

Aman Dangi  

## License

This project is licensed under the MIT License - see the LICENSE.txt file for details
