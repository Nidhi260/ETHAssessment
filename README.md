**MyToken Smart Contract**


**Introduction**
The MyToken smart contract is a basic implementation of an ERC20-like token on the Ethereum blockchain. This contract allows for the minting and burning of tokens, enabling the total supply and balances of token holders to be managed. The token is named "META" with the abbreviation "MTA".

**Requirements**

**Public Variables:**

**tokenName**: Stores the name of the token.

**tokenAbbrv**: Stores the abbreviation of the token.

**totalSupply**: Stores the total supply of the tokens.

**Mapping**:

**balances**: Maps addresses to their respective token balances.

**Mint Function**:

1. Increases the total supply by a specified value.
   
2.Increases the balance of the specified address by the same value.

**Burn Function:**

1.Decreases the total supply by a specified value.

2.Decreases the balance of the specified address by the same value.

3.Ensures that the balance of the specified address is greater than or equal to the amount to be burned.

**Contract Overview**

**Public Variables**

**tokenName**: A string that holds the name of the token.

**tokenAbbrv**: A string that holds the abbreviation of the token.

**totalSupply**: An unsigned integer that holds the total supply of the token.

**Mapping**

**balances**: A mapping that associates each address with its corresponding token balance.

**Functions**

**Mint Function**

function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}

**Purpose**: Increases the total supply of tokens and the balance of the specified address.

**Parameters:**
_address: The address of the token holder.
_value: The amount of tokens to mint.

**Behavior**: Adds the specified value to the total supply and to the balance of the specified address.

**Burn Function**

function burn(address _address, uint _value) public {
    if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}

**Purpose**: Decreases the total supply of tokens and the balance of the specified address.

**Parameters**:
_address: The address of the token holder.
_value: The amount of tokens to burn.

**Behavior**: Checks if the balance of the specified address is greater than or equal to the value to be burned. If true, subtracts the specified value from the total supply and the balance of the specified address.

**Usage**
To use the MyToken contract, deploy it to the Ethereum blockchain. Once deployed, you can interact with the contract using its public variables and functions.

**Example**

**Minting Tokens**:

myToken.mint(0xYourAddress, 100);
This will mint 100 tokens and add them to the balance of the specified address.

**Burning Tokens**:

myToken.burn(0xYourAddress, 50);
This will burn 50 tokens from the balance of the specified address, provided the address has at least 50 tokens.

**License**

This project is licensed under the MIT License. See the LICENSE file for more details.





