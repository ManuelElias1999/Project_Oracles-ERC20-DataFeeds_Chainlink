# Chainlink Bootcamp 2024 Token and Token Shop

This repository contains two smart contracts developed for the Chainlink Bootcamp 2024 program: a token contract and a token shop contract. Both contracts leverage the capabilities of the Ethereum blockchain and integrate with Chainlink oracles for enhanced functionality.

## Token Contract - Chainlink Bootcamp 2024 Token (Zeus)

The "Chainlink Bootcamp 2024 Token Zeus" (symbol: CLBoot24Zeus) is an ERC20 token designed to serve as a digital asset within the Chainlink Bootcamp 2024 ecosystem.

### Features

- **ERC20 Compliance**: The token contract adheres to the ERC20 standard, making it interoperable with various decentralized applications, exchanges, and wallets that support ERC20 tokens.
- **Role-Based Access Control**: The contract implements a role-based access control mechanism using OpenZeppelin's AccessControl library. Two roles are defined: `DEFAULT_ADMIN_ROLE` and `MINTER_ROLE`. The default admin role is granted to the contract deployer, allowing them to manage roles and other administrative tasks. The minter role is responsible for minting new tokens.
- **Decimal Precision**: The token has two decimal places, providing flexibility in representing fractional amounts of the token.

### Usage

1. **Deployment**: Deploy the contract on the Ethereum blockchain.
2. **Role Assignment**: Upon deployment, the contract deployer automatically receives both the default admin role and the minter role.
3. **Minting Tokens**: Use the `mint` function to create new units of the token and assign them to a specific address. Only accounts with the `MINTER_ROLE` can call this function.

## Token Shop Contract

The Token Shop contract allows users to purchase tokens using Ether (ETH) and integrates with Chainlink oracles to obtain real-time ETH/USD price feeds for accurate token pricing.

### Features

- **Token Purchase with ETH**: Users can buy tokens by sending ETH to the contract's fallback function. The amount of tokens received is calculated based on the ETH amount sent and the current ETH/USD exchange rate.
- **Chainlink Oracle Integration**: The contract interfaces with the Chainlink oracle to fetch the current ETH/USD price. It utilizes the `AggregatorV3Interface` contract to obtain reliable and decentralized price feeds.
- **Owner Withdrawal**: The contract owner can withdraw the ETH balance held by the contract to their designated address using the `withdraw` function.
- **Safety Measures**: The contract includes a modifier `onlyOwner` to restrict certain functions, such as withdrawal, to the contract owner for enhanced security.

### Usage

1. **Deployment**: Deploy the contract on the Ethereum blockchain, providing the token contract address as an argument to the constructor.
2. **Token Purchase**: Users can interact with the contract by sending ETH to the contract address. The contract automatically converts the received ETH into tokens based on the current exchange rate.
3. **Owner Withdrawal**: The contract owner can use the `withdraw` function to withdraw the ETH balance accumulated in the contract to their account.

## Chainlink Oracle Integration

Both contracts leverage the capabilities of Chainlink oracles to enhance their functionality:

- **Token Shop**: The Token Shop contract integrates with Chainlink oracles to fetch real-time ETH/USD price feeds. This ensures that token prices remain accurate and reflective of current market conditions.

