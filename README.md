Project Title
SimpleContract

Simple overview of use/purpose.
A simple smart contract demonstrating the use of require(), assert(), and revert() statements in Solidity.

Description
This project provides a basic example of a Solidity smart contract that uses require(), assert(), and revert() statements to enforce conditions and handle errors. 
The contract allows the owner to increment, decrement, and reset a counter while ensuring specific conditions are met. The purpose is to showcase how these statements
can be utilized in a smart contract.

Getting Started
open a solidity compiler.

solidity

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SimpleContract {
    address public owner;
    uint256 public count;

    constructor() {
        owner = msg.sender;
    }

    // Function to increment the count
    function increment() public {
        require(msg.sender == owner, "Only the owner can increment the count");
        count += 1;
        assert(count > 0); // Assert that count is always positive
    }

    // Function to decrement the count
    function decrement() public {
        require(msg.sender == owner, "Only the owner can decrement the count");
        if (count == 0) {
            revert("Count is already zero, cannot decrement");
        }
        count -= 1;
        assert(count >= 0); // Assert that count is never negative
    }

    // Function to reset the count
    function resetCount() public {
        require(msg.sender == owner, "Only the owner can reset the count");
        count = 0;
    }
}

Create a new file and paste the above code.

Compile the contract by selecting the appropriate compiler version (0.8.0 or higher) and clicking on the "Compile" button.

Deploy the contract:

Go to the "Deploy & Run Transactions" tab.
Select the environment (e.g., JavaScript VM for a local environment).
Click on the "Deploy" button.
Help
Ensure you have a Solidity development environment like Remix IDE.
Make sure you are using the correct Solidity compiler version (0.8.0 or higher).
If you encounter any issues, refer to the Remix documentation or Solidity documentation.
Authors
Annu
22BCS10069
@Annu1603

License
This project is licensed under the MIT License - see the LICENSE.md file for details.








