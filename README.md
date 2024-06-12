
# Project Title

Getting Started with Solidity
Project: Create a Token

## Description

 we will create a contract together to fulfill the following requirements:

1) Contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
2) Contract will have a mapping of addresses to balances (address => uint)
3) It will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount.
4) Contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the address.
5) Lastly, burn function  have conditionals to make sure the balance of account is greater than or equal to the amount that is supposed to be burned.

## Getting Started
### Installing

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., mytoken.sol). Copy and paste the following code into the file:

```
//SPDX-License-identifier:MIT
pragma solidity 0.8.18;

contract MyToken{
    //Public variable to store token details
    string public name="MyToken";
    string public symbol="MTK";
    uint256 public totalSupply;

    // mapping addresss to balances
    mapping(address=>uint256)public balances;
    //Mint function to create new token 
    function mint(address _to , uint256 _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    //function to destroy tokens
    function burn(address _from,uint256 _value) public{
        require(balances[_from]>=_value,"Insufficient balance to burn");
        totalSupply -= _value;
        balances[_from] -= _value;
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the ("Compile "the name of the file" ") for ex. comple first.sol button.
Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "first.sol" contract from the dropdown menu, and then click on the "Deploy" button.
then u can see a the below of the option ' Deployed/Unpinned Contracts ' expand it and balances mint burn etc and now u can see our code is ready to run .


## Authors

Contributors names and contact info

sudhish tiwari

email : sudhish0906004@gmail.com

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
