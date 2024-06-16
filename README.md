# Mytoken Contract

This is a simple solidity program that is used to mint and burn the tokens for a particular address

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has two functions burn and mint that are used to mint and destroy the supply of tokens for the particular address, these actions will also affect the total supply. This program is also using mapping to map the adresses to balances. Mapping is used to store the key value pairs in solidity.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
contract MyToken {

    string public Token_Name = "Ether";
    string public Token_Abbrv = "ETH";
    uint public TotalSupply;
    
    mapping (address=>uint) public balance;

    function mint(address addr,uint value) external{
        TotalSupply += value;
        balance[addr] += value;
    }
    function burn(address addr,uint value) external{
        if(balance[addr]>= value){
            TotalSupply -= value;
            balance[addr] -= value;
        }
    }

}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar, and then click on the "Project.sol" button.
Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken-Project.sol" contract from the dropdown menu, and then click on the "Deploy" button.
Once the contract is deployed, you can interact with it by calling the mint or burn function. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "mint" function to add the tokens to a particular address. Click on "Burn" function to destroy the tokens from a particular address.

## Authors

Ritvik Jindal
www.linkedin.com/in/ritvik-jindal05


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
