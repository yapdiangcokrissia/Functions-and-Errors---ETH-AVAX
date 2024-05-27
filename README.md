# ErrorHandlingContract

This is a simple Solidity smart contract demonstrating basic error handling mechanisms, including `require`, `assert`, and `revert`. The contract includes functions to set a value, perform division, and show examples of using assertions and reverts.

## Smart Contract Code

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract ErrorHandlingContract {
    uint public value;

    function setValue(uint _newValue) public {
        require(_newValue != 0, "New value must not be zero");
        assert(_newValue != value);
        value = _newValue;
    }
    
    function divide(uint _numerator, uint _denominator) public pure returns (uint) {
        require(_denominator != 0, "Denominator cannot be zero");
        return _numerator / _denominator;
    }
    
    function assertExample(uint _input) public pure returns (uint) {
        assert(_input > 0);
        return _input * 2;
    }
    
    function revertExample() public pure {
        revert("This transaction has been reverted");
    }
}
```

## Functions

### `setValue(uint _newValue)`

This function sets a new value to the contract's state variable `value`. It includes two error checks:
- `require(_newValue != 0, "New value must not be zero");`: Ensures the new value is not zero.
- `assert(_newValue != value);`: Ensures the new value is different from the current value.

### `divide(uint _numerator, uint _denominator)`

This function performs division of two unsigned integers. It includes an error check:
- `require(_denominator != 0, "Denominator cannot be zero");`: Ensures the denominator is not zero.

Returns the result of the division.

### `assertExample(uint _input)`

This function multiplies the input by 2. It includes an error check:
- `assert(_input > 0);`: Ensures the input is greater than zero.

Returns the result of the multiplication.

### `revertExample()`

This function always reverts the transaction with a custom error message:
- `revert("This transaction has been reverted");`: Reverts the transaction with the provided message.

## Deployment

To deploy this contract, use the following steps:

1. Install [Remix IDE](https://remix.ethereum.org/) or any Ethereum development environment of your choice.
2. Create a new file and paste the smart contract code above.
3. Compile the contract using the Solidity compiler.
4. Deploy the contract to a local or test Ethereum network.

## Usage

After deploying the contract, you can interact with it using the following methods:

- **setValue(uint _newValue):** Set a new value for the `value` state variable.
- **divide(uint _numerator, uint _denominator):** Perform division with the provided numerator and denominator.
- **assertExample(uint _input):** Multiply the input by 2, ensuring the input is greater than zero.
- **revertExample():** Always reverts the transaction with a custom message.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
