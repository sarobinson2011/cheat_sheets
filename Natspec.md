# Natspec (natural specification)

Natspec is short for "Natural Specification," and it's a way to document Ethereum smart contracts in a human-readable format. 
These comments are parsed by tools like the Solidity compiler and can be extracted to generate documentation for the contract.

- @title Contract Title
- @notice Description of what the contract does (for end-users)
- @dev Detailed explanation for developers

### Example:
// @title TokenSale.
// @notice Manages the sale of tokens to investors.
// @dev This contract handles token purchases, refunds, and pricing.

- @title: Describes the title or name of the contract.
- @notice: Provides a high-level description of what the contract does. This is for end-users or consumers of the contract.
- @dev: Offers detailed explanations, implementation notes, or information for developers working on or reviewing the contract's code.

You can include these comments above functions, state variables, or any significant sections of your Solidity code to document your contract effectively.
