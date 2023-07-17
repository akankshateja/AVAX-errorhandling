# AVAX-errorhandling
This is a Solidity smart contract that demonstrates different error handling techniques using assert, revert, and require functions.
# Description
This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has 4 functions to handle the error in a different manner or by using different functions require(), revert(), assert() and the one function is just to set the age. In this Eligible Criteria contract basically, it will check whether your age limit is eligible or not for the vote through this 3 error handling function. This program serves as a simple and straightforward introduction to Error handling and can be used as a stepping stone for more complex projects in the future for handling error in the contract.
# Getting Started
# Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol).
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract AssertionContract {
    uint256 public totalValue;
    function updateValue(uint256 newValue) external {
        require(newValue > 0, "Value must be greater than zero");
        uint256 oldValue = totalValue;
        assert(newValue != oldValue);
        totalValue = newValue;
    }
    function withdraw(uint256 amount) external {
        require(amount <= totalValue, "Insufficient balance");
        if (amount > totalValue) {
            revert("Withdrawal failed");
        }
        
        totalValue -= amount;
    }
}
```
It declares a state variable totalValue of type uint256, representing the total value stored in the contract.
The updateValue function allows external callers to update the value of totalValue. It takes a newValue parameter and checks that it is greater than zero using a require statement. 
Then it assigns the current value of totalValue to the oldValue variable, and asserts that the newValue is not equal to the oldValue. Finally, it updates the totalValue with the newValue.
The withdraw function allows external callers to withdraw a certain amount from the totalValue. It takes an amount parameter and checks that it does not exceed the totalValue using a require statement.
If the amount is greater than the totalValue, it reverts the transaction with an error message. Otherwise, it subtracts the amount from the totalValue.
# Authors
Metacrafter Chris
@metacraftersio

# License
This project is licensed under the MIT License - see the LICENSE.md file for details
