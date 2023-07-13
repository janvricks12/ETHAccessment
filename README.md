# ETH Accessment Test

Hello, this is my ETH Accessment test for my ETH Beginners module.


## Description

This is what my project is, it's a token contract that is made using solidarity.

## Getting Started

### Tools

* My program is made using Remix Ethereum.
* [remix.ethereum.org](https://remix.ethereum.org/)

### Executing program

* First we start following the steps on the accessment.
* Step 1:
    Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
```
    string public tokenName = "VICENCIO";
    string public tokenAbbrv = "SPEC";
    uint public totalSupply = 0;
```
  the first two is only a namesake. But the last is the total supply which shows
  the total balances of the account.


* Step 2:
    Your contract will have a mapping of addresses to balances (address => uint)
```
mapping(address => uint) public balances;
```
  this allows you to put your address.
  which is in the deploy and compile.
  "0x000000000"


* Step 3:
    You will have a mint function that takes two parameters: an address and a value. 
    The function then increases the total supply by that number and increases the balance 
    of the “sender” address by that amount
```
function mint (address _address,uint _value) public {
        totalSupply += _value;
        balances[_address] +=  _value;
```


* Step 4:
      Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
      It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
      and from the balance of the “sender”.
```
function burn (address _address,uint _value) public {
        totalSupply -= _value;
        balances[_address] -=  _value;
}
```


* Step 5:
       Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
```
if(balances[_address] >= _value)
```
And if you combine them together, the full code will be.

```
contract MyToken {

    // public variables here
    string public tokenName = "VICENCIO";
    string public tokenAbbrv = "SPEC";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address,uint _value) public {
        totalSupply += _value;
        balances[_address] +=  _value;

    }   
    // burn function
    function burn (address _address,uint _value) public {
        if(balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -=  _value;
        }
    }   
}
```


## Authors

ex. Jan Vricks Vicencio

gmail. 8210348@ntc.edu.ph


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
