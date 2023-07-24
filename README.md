# AVAX_MODULE1_FUNCTION_AND_ERROR

Functions in AVAX Smart Contracts:

Functions in AVAX smart contracts are operations or actions that can be executed on the blockchain.
These functions can modify the state of the contract, read data from the contract, or interact with other contracts.
Functions can have different visibility levels, such as public, external, internal, and private, defining who can call the function and from where.


Handling Errors in AVAX Smart Contracts:

Errors can occur in smart contracts due to various reasons, such as invalid inputs, insufficient funds, or failed contract execution.

To handle errors, smart contracts can use various mechanisms like require, assert, and revert.

require: The require statement is used to validate conditions and revert the transaction if the condition is not met. It is commonly used for input validation.

assert: The assert statement is used to check for conditions that should never be false. If the condition evaluates to false, the transaction will revert, indicating a critical error or unexpected state.

revert: The revert statement is used to revert the transaction with an optional error message. It is typically used to handle certain business logic errors or invalid states.

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

CODE......

contract ErrorHandlingContract {
    uint256 public myValue;

    function setValue(uint256 newValue) public {
        // Use require to check for valid input
        require(newValue > 0, "Value must be greater than zero");

        // Set the value if the input is valid
        myValue = newValue;
    }

    function withdraw() public {
        // Use revert to handle a specific scenario (e.g., insufficient balance)
        require(myValue > 100, "Insufficient balance");

        // Withdraw logic
        // ...
    }
}
