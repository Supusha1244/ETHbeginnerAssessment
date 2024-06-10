# MyToken Smart Contract

#### Overview
MyToken is a simple Ethereum smart contract for creating and managing a custom token named Supusha with the symbol SPB. This contract includes functionalities to mint and burn tokens, thereby increasing or decreasing the total supply respectively.




## Implementation Details

#### Public Variables
 - tokenName: The name of the token, which is Supusha.
 - tokenAbbrv: The abbreviation of the token, which is SPB.
 - totalSupply: The total supply of the tokens.

#### Mappings
- balances: A mapping that associates addresses with their respective token balances.

#### Functions
The contract includes the following functions:

#### mint
This function allows for the creation of new tokens. It increases the total supply and the balance of a specified address.
```bash
  function mint(address _to, uint256 _value) public {
    totalSupply += _value;
    balances[_to] += _value;
}
```
#### burn
This function allows for the destruction of existing tokens. It decreases the total supply and the balance of a specified address.
```bash
  function burn(address _from, uint256 _value) public {
    require(balances[_from] >= _value, "Insufficient balance to burn");
    totalSupply -= _value;
    balances[_from] -= _value;
}

```


## Usage
#### Minting Tokens
To mint new tokens, call the mint function with the address that will receive the tokens and the number of tokens to be created.

```bash
  mint(address _to, uint256 _value)
```
#### Burning Tokens
To burn existing tokens, call the burn function with the address from which the tokens will be taken and the number of tokens to be destroyed.
```bash
  burn(address _from, uint256 _value)

```


