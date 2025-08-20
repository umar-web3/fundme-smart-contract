# FundMe Smart Contract  

A Solidity smart contract for decentralized crowdfunding.  
This project allows anyone to send ETH to the contract (funding), with a minimum funding requirement in USD enforced using Chainlink Price Feeds.  
The owner of the contract can securely withdraw the funds.  


Features:  
- Accepts ETH funding from multiple users.  
- Enforces a minimum USD value for funding.  
- Uses Chainlink Price Feeds to fetch real-time ETH/USD price.  
- Keeps track of all funders and their contribution amounts.  
- Only the contract owner can withdraw funds.  
- Includes fallback and receive functions to handle direct ETH transfers.  



Project Structure:
fundme-smart-contract/
│
├── FundMe.sol # Main crowdfunding contract
│── PriceConverter.sol # Library for ETH → USD conversion
│
├── README.md # Project documentation




Tech Stack: 
- Solidity ^0.8.24  
- Chainlink Oracles (Price Feeds)  
- Ethereum / Testnets (Sepolia recommended)  



 How It Works:
1. Users call the `fund()` function and send ETH.  
2. The contract checks if the sent ETH ≥ minimum USD value (using Chainlink price feed).  
3. If valid, the sender’s address and amount are stored.  
4. The contract owner can later call `withdraw()` to collect all ETH.  



 Deployment & Usage:  
- Deploy `FundMe.sol` using Remix, Hardhat, or Foundry.  
- Make sure Chainlink Price Feed contract address is set correctly for the network.  
- Example (Sepolia ETH/USD feed): `0x694AA1769357215DE4FAC081bf1f309aDC325306`  
- Call `fund()` with ETH → must meet the USD minimum.  
- Owner can call `withdraw()` anytime.  



Future Improvements: 
- Add events for `Funded` and `Withdrawn`.  
- Add front-end DApp integration.  
- Support multiple ERC20 tokens instead of only ETH.  



License  
This project is licensed under the MIT License.  






├── README.md # Project documentation
└── LICENSE # License info (MIT)
