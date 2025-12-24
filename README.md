# TIP20-Factory
TIP20 token creation smart contract interfaces in Solidity
pragma solidity ^0.8.0; 

interface ITIP20 {} 

interface ITIP20Factory {
    function createToken(
        string memory name,
        string memory symbol,
        string memory currency,
        ITIP20 quoteToken,
        address admin
    ) external returns (address token);
 
    function isTIP20(address token) external view returns (bool);
 
    function tokenIdCounter() external view returns (uint256);
 
    event TokenCreated(
        address indexed token,
        uint256 indexed id,
        string name,
        string symbol,
        string currency,
        ITIP20 indexed quoteToken,
        address admin
    );
 
    error InvalidQuoteToken();
}
