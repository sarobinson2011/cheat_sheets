# Natspec (natural specification)

Natspec is short for "Natural Specification," and it's a way to document Ethereum smart contracts in a human-readable format.
These comments are parsed by tools like the Solidity compiler and can be extracted to generate documentation for the contract.
    
    ◦ @title Contract Title
    ◦ @notice Description of what the contract does (for end-users)
    ◦ @dev Detailed explanation for developers

- @title: Describes the title or name of the contract.
- @notice: Provides a high-level description of what the contract does. This is for end-users or consumers of the contract.
- @dev: Offers detailed explanations, implementation notes, or information for developers working on or reviewing the contract's code.

Standard convention is to use 3 comment marks e.g. /// to indicate a Natspec comment

### Example:

    ◦ /// @title TokenSale
    ◦ /// @notice Manages the sale of tokens to investors.
    ◦ /// @dev This contract handles token purchases, refunds, and pricing.

You can include these comments above functions, state variables, or any significant sections of your Solidity code to document your contract effectively.


### Template :

    /// @title A title that should describe the contract/interface
    /// @author The name of the author
    /// @notice Explain to an end user what this does
    /// @dev Explain to a developer any extra details

## Full list of Natspec comment tags:
    
    - @title         A title that should describe the contract/interface 	contract, library, interface
    - @author        The name of the author 	                            contract, library, interface
    - @notice        Explain to an end user what this does 	                contract, library, interface, function, public state variable, event
    - @dev           Explain to a developer any extra details 	            contract, library, interface, function, state variable, event
    - @param         Documents a parameter (followed by parameter name) 	function, event
    - @return        Documents return variables of a contract’s function 	function, public state variable
    - @inheritdoc    Copies all missing tags from the base function (must be followed by the contract name) 	function, public state variable
    - @custom:...    Custom tag, semantics is application-defined 	        everywhere
    ◦ @notice        Description of what the contract does                 (for end-users)
    
