Overview
MyToken is a simple ERC20-like token contract written in Solidity. This contract allows users to deposit, withdraw, and transfer tokens. It includes functionality for an owner to set the maximum transaction amount.

Contract Details
Total Supply: The total supply of tokens in circulation.
Max Transaction: The maximum amount of tokens that can be transferred in a single transaction.
Owner: The address of the contract owner (initially set to the deployer of the contract).
Functions
constructor()
Initializes the contract.
Sets the deployer as the contract owner.
deposit(address _address, uint _number)
Allows depositing of tokens to a specified address.
Increases the total supply and balance of the specified address.
Parameters:
_address: The address to deposit tokens to.
_number: The amount of tokens to deposit.
Requirements:
_number must be greater than 0.
withdraw(address _address, uint _number)
Allows withdrawal of tokens from a specified address.
Decreases the total supply and balance of the specified address.
Parameters:
_address: The address to withdraw tokens from.
_number: The amount of tokens to withdraw.
Requirements:
The balance of _address must be greater than or equal to _number.
_number must not exceed Max_transaction.
transfer(address _to, uint _amount)
Allows transferring of tokens from the caller's address to another address.
Parameters:
_to: The address to transfer tokens to.
_amount: The amount of tokens to transfer.
Requirements:
_amount must be greater than 0.
The balance of the caller must be greater than or equal to _amount.
changeMaxTransaction(uint _newMax)
Allows the contract owner to change the maximum transaction amount.
Parameters:
_newMax: The new maximum transaction amount.
Requirements:
Only the contract owner can call this function.
Modifiers
onlyOwner
Ensures that only the contract owner can call the function.
