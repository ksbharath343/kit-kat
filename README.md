# kit-kat

## Overview

The `KitKatChocolateQualityCheck` contract is a simple Solidity smart contract designed to track the quality check status of KitKat chocolate batches. It ensures that each batch undergoes a quality check process only once and maintains a record of which batches have passed the quality check.

## Features

1. **Perform Quality Check**: Mark a specific batch of KitKat chocolate as having passed a quality check.
2. **Check Quality Status**: Verify if a specific batch of KitKat chocolate has passed the quality check.

## Functions

### `performQualityCheck(uint256 kitkatChocolateBatchId)`

This function marks a specific KitKat chocolate batch as having passed the quality check. It ensures that the batch ID is valid and that the quality check has not been performed on this batch before.

- **Parameters**:
  - `kitkatChocolateBatchId`: The ID of the KitKat chocolate batch to be checked.
  
- **Requirements**:
  - The `kitkatChocolateBatchId` must be greater than 10.
  - The batch must not have already undergone a quality check.
  
- **Reverts**:
  - If the `kitkatChocolateBatchId` is 10 or less.
  - If the quality check has already been performed for the specified batch.

### `isQualityCheckPassed(uint256 kitkatChocolateBatchId)`

This function checks if a specific KitKat chocolate batch has passed the quality check.

- **Parameters**:
  - `kitkatChocolateBatchId`: The ID of the KitKat chocolate batch to be verified.

- **Returns**:
  - `true` if the batch has passed the quality check.
  
- **Asserts**:
  - That the batch has undergone a quality check.

## Usage

### Deployment

Deploy the contract using any Ethereum development environment like Remix, Hardhat, or Truffle.

### Performing a Quality Check

Call the `performQualityCheck` function with the batch ID of the KitKat chocolate to mark it as having passed the quality check.

```solidity
performQualityCheck(11); // Example batch ID
```

### Checking Quality Status

Call the `isQualityCheckPassed` function with the batch ID of the KitKat chocolate to verify if it has passed the quality check.

```solidity
isQualityCheckPassed(11); // Example batch ID
```

## Notes

- Ensure that the batch ID is greater than 10 when performing a quality check.
- The contract maintains a mapping of batch IDs to their quality check status.
- Attempting to perform a quality check on a batch that has already been checked will result in a revert.
- The `isQualityCheckPassed` function asserts that the batch has indeed passed a quality check, ensuring accurate results.

## License

This project is licensed under the MIT License.
