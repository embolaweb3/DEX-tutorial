## Table of Contents
1. [Introduction](#introduction)
2. [Smart Contract Overview](#smart-contract-overview)
    - [Smart Contract Features](#smart-contract-features)
3. [Setting Up Development Environment](#setting-up-development-environment)
    - [Requirements](#requirements)
    - [Installation](#installation)
4. [Understanding the Smart Contract](#understanding-the-smart-contract)
    - [Contract Structure](#contract-structure)
    - [Contract Functionalities](#contract-functionalities)
5. [Contract Functions](#contract-functions)
    - [Constructor](#constructor)
    - [Admin Functions](#admin-functions)
    - [Token Management](#token-management)
    - [Balances Management](#balances-management)
    - [Order Management](#order-management)
6. [Deploying and Interacting with the Contract](#deploying-and-interacting-with-the-contract)
    - [Deployment](#deployment)
    - [Interacting with the Contract](#interacting-with-the-contract)
7. [Conclusion](#conclusion)
    - [Summary](#summary)
    - [Next Steps](#next-steps)
    - [Resources](#resources)

## Introduction

Decentralized exchanges (DEXs) have revolutionized the way users trade cryptocurrencies by eliminating the need for intermediaries and providing a trustless, non-custodial trading experience. In this comprehensive tutorial, we'll delve into the world of decentralized finance (DeFi) on the Celo blockchain and learn how to build our own decentralized exchange using Solidity.

### What is Celo?

Celo is a blockchain platform focused on making financial tools accessible to anyone with a mobile phone. It offers fast, secure, and low-cost transactions, making it an ideal choice for building decentralized applications (dApps) that empower users in emerging markets and beyond.

### Why Build a Decentralized Exchange on Celo?

Decentralized exchanges on Celo offer several advantages over traditional exchanges and even other blockchain platforms:

- **Accessibility**: Celo's mobile-first approach ensures that users can access the exchange easily, even with limited internet connectivity.
- **Affordability**: Celo's low transaction fees make trading on the decentralized exchange cost-effective for users of all income levels.
- **Inclusivity**: By leveraging Celo's platform, we can build financial infrastructure that reaches the underserved and unbanked populations, fostering financial inclusion worldwide.
- **Security**: Decentralized exchanges on Celo benefit from the security guarantees provided by the blockchain, such as immutability and censorship resistance.

Let's dive in and start building our decentralized exchange on Celo!

## Smart Contract Overview

In this section, we'll provide an overview of the Solidity smart contract that powers our decentralized exchange on the Celo blockchain. This smart contract is responsible for managing token balances, handling order creation and fulfillment, and facilitating token swaps between users.

### Smart Contract Features

Our decentralized exchange smart contract includes the following key features:

- **Token Management**: Users can deposit and withdraw ERC-20 tokens supported by the exchange.
- **Order Management**: Users can create buy and sell orders to trade tokens with other users.
- **Trade Execution**: Orders are matched and executed atomically, ensuring fair and efficient trading.
- **Event Logging**: Events are emitted for important actions such as token deposits, order creation, and trade execution, providing transparency and auditability.

The smart contract is implemented using Solidity, the programming language of the Ethereum Virtual Machine (EVM), and follows best practices for security, efficiency, and gas optimization.

### Contract Structure

The smart contract consists of several components, including:

1. **State Variables**: Variables to store token balances, order information, and contract admin.
2. **Events**: Event declarations to log important contract actions.
3. **Modifiers**: Modifiers to restrict access to certain functions based on conditions (e.g., only admin).
4. **Functions**: Public and external functions to interact with the contract, including depositing tokens, creating orders, and filling orders.

The contract is modular and well-organized, making it easy to understand and extend with additional functionalities if needed.

In the next sections, we'll dive deeper into each component of the smart contract and explain how it contributes to the overall functionality of our decentralized exchange on Celo.

## Setting Up Development Environment

In this section, we'll guide you through setting up your development environment for building a decentralized exchange (DEX) on the Celo blockchain using Remix, an online Solidity IDE (Integrated Development Environment). Remix provides a user-friendly interface for writing, testing, and deploying smart contracts directly from your web browser.

### Requirements

Before we begin, ensure you have the following:

1. **Web Browser**: Make sure you have a modern web browser such as Google Chrome, Mozilla Firefox, or Brave.
2. **Internet Connection**: Ensure you have a stable internet connection to access the Remix IDE.
3. **Celo Wallet**: Install a Celo-compatible wallet extension like MetaMask or Valora to interact with Celo contracts and transactions.
4. **Celo Faucet** Obtain celo alfajores token to your wallet. Visit [Celo faucet](https://faucet.celo.org/alfajores) 

### Installation

Follow these steps to set up your development environment with Remix:

1. **Open Remix IDE**: Visit the [Remix website](https://remix.ethereum.org/) to launch the Remix IDE.
2. **Create New File**: Click on the "+" icon in the file explorer panel to create a new file for your Solidity smart contract.
3. **Write Solidity Code**: Write or paste your Solidity smart contract code into the editor. You can also import existing contracts from GitHub or your local filesystem.
4. **Compile Contract**: Click on the "Solidity Compiler" tab in the sidebar and select the appropriate compiler version for your contract. Click "Compile" to compile your contract code.
5. **Deploy Contract**: Once compiled successfully, switch to the "Deploy & Run Transactions" tab. Select the desired environment (e.g., JavaScript VM, Injected Web3, Celo) and click "Deploy" to deploy your contract to the selected network.

### Using Remix with Celo

To interact with Celo contracts and transactions in Remix, you'll need to connect Remix to a Celo network node. Follow these steps to connect Remix to a Celo node:

1. **Select Celo Environment**: In Remix, go to the "Deploy & Run Transactions" tab and select "Celo" as the environment.
2. **Configure Celo Node**: Click on the "Settings" icon in the sidebar and scroll down to the "Plugin" section. Under "Celo", enter the URL of a Celo network node (e.g., `https://forno.celo.org`) and click "Connect" to connect Remix to the Celo network.
3. **Account Configuration**: If using MetaMask, ensure that MetaMask is set to the Celo network and that you have selected the appropriate account with sufficient funds for deploying and interacting with contracts.

With Remix configured to work with Celo, you can now write, compile, and deploy your decentralized exchange smart contract directly from your web browser.

In the next section, we'll dive into understanding the structure and components of our decentralized exchange smart contract written in Solidity.

## Understanding the Smart Contract

In this section, we'll explore the structure and components of the Solidity smart contract that powers our decentralized exchange (DEX) on the Celo blockchain. Understanding the smart contract's architecture and functionalities is essential for effectively building, testing, and deploying our decentralized exchange.

### Contract Structure

Our smart contract is structured to efficiently manage token balances, handle order creation and fulfillment, and facilitate token swaps between users. Here's an overview of its components:

1. **State Variables**: Variables to store token balances, order information, contract admin, and other essential data.
   
2. **Events**: Event declarations to log significant contract actions such as token deposits, order creation, and trade execution. Events provide transparency and auditability.

3. **Modifiers**: Modifiers to enforce access control and conditions on certain functions. For example, the `onlyAdmin` modifier restricts access to admin-only functions.

4. **Functions**: Public and external functions to interact with the contract. These functions include depositing tokens, creating orders, filling orders, and other essential operations for trading on the DEX.

### Contract Functionalities

Our decentralized exchange smart contract provides the following key functionalities:

- **Token Management**: Users can deposit and withdraw ERC-20 tokens supported by the exchange. The contract maintains balances for each token and user.

- **Order Management**: Users can create buy and sell orders specifying the token pair, order type, and desired quantity. Orders are stored in a public array and matched based on price and availability.

- **Trade Execution**: Orders are matched and executed atomically to ensure fair and efficient trading. Trades result in token transfers between users, with appropriate balances updated accordingly.

- **Event Logging**: Events are emitted for important contract actions, allowing users and external observers to monitor and track the exchange's activity.

## Contract Functions
In this section, we'll delve into the functions implemented in our Solidity smart contract to facilitate the operation of our decentralized exchange (DEX) on the Celo blockchain. These functions handle various aspects of token management, order creation and fulfillment, and trade execution, enabling users to interact seamlessly with the exchange.


### SPDX-License-Identifier

```solidity
// SPDX-License-Identifier: MIT
```

#### Explanation:
- SPDX-License-Identifier is a special comment recognized by various tools and platforms to specify the license under which the code is distributed.

### Solidity Version Pragma

```solidity
pragma solidity 0.8.0;
```

#### Explanation:
- The Solidity version pragma specifies the version of the Solidity compiler to be used for compiling the contract.
- `^0.8.0` indicates that the contract can be compiled using any compiler version starting from version 0.8.0 up to, but not including, version 0.9.0.

### Interface IERC20

```solidity
interface IERC20 {
    function transfer(address recipient, uint256 amount) external returns (bool);
    function transferFrom(address sender, address recipient, uint256 amount) external returns (bool);
    function balanceOf(address account) external view returns (uint256);
    function approve(address spender, uint256 amount) external returns (bool);
}
```

#### Explanation:

- The interface declares four functions required by the ERC-20 standard: `transfer`, `transferFrom`, `balanceOf`, and `approve`.
- The `transfer` function allows the token contract to transfer tokens to a specified recipient.
- The `transferFrom` function allows authorized addresses to transfer tokens from one account to another.
- The `balanceOf` function returns the balance of tokens for a given account.
- The `approve` function allows an address (spender) to spend tokens on behalf of the token owner, up to the specified amount.
  
### Addresses
```solidity
    address public admin;
    mapping(address => mapping(address => uint256)) public balances;
    mapping(address => bool) public tokens;
```
### Explanation
- `admin`: Stores the address of the contract admin, who has special privileges.
- `balances`: Maps token balances for each user on the exchange. It tracks the amount of each token held by each user.
- `tokens`: Tracks the supported tokens on the exchange by mapping token addresses to boolean values, indicating whether a token is supported or not.

These state variables are essential for managing user balances, supporting tokens, and controlling administrative functions within the decentralized exchange smart contract.

### Events
```solidity
event TokenAdded(address indexed token);
event TokenRemoved(address indexed token);
event Trade(address indexed tokenGive, uint256 amountGive, address indexed tokenGet, uint256 amountGet);
event OrderCreated(address indexed tokenGive, uint256 amountGive, address indexed tokenGet, uint256 amountGet, address indexed creator);
event OrderFilled(address indexed tokenGive, uint256 amountGive, address indexed tokenGet, uint256 amountGet, address indexed filler);
```
#### Explanation:
- `TokenAdded`: Signals the addition of a new token to the exchange.
- `TokenRemoved`: Indicates the removal of a token from the exchange.
- `Trade`: Represents a trade event, specifying token pairs and trade amounts.
- `OrderCreated`: Marks the creation of a new order, including token pairs, amounts, and creator.
- `OrderFilled`: Denotes the successful filling of an order, specifying token pairs, amounts, and filler.

These events provide essential notifications about token management, trades, and order activities within the decentralized exchange.

### `struct Order`

```solidity
struct Order {
    address tokenGive;
    uint256 amountGive;
    address tokenGet;
    uint256 amountGet;
    address creator;
}
```

#### Explanation:
- This is a struct named `Order`, which represents an order placed on the decentralized exchange.
- It encapsulates the details of an order, including the tokens involved, the amounts to be exchanged, and the creator of the order.
- The struct has the following fields:
  - `tokenGive`: The address of the token to be given by the user placing the order.
  - `amountGive`: The amount of `tokenGive` to be given by the user placing the order.
  - `tokenGet`: The address of the token to be received by the user placing the order.
  - `amountGet`: The amount of `tokenGet` to be received by the user placing the order.
  - `creator`: The address of the user who created the order.
- By defining this struct, the contract can conveniently group together the various attributes of an order, making it easier to manage and manipulate orders within the exchange.

### `Order[] public orders;`

#### Explanation:
- This is a public state variable named `orders`, which is an array of `Order` structs.
- This array provides a way to track and manage the orders placed on the exchange, facilitating order creation, retrieval, and management functionalities.


### Constructor

```solidity
constructor() {
    admin = msg.sender;
}
```

#### Explanation:
- The constructor is a special function that is automatically executed once when the contract is deployed.
- In our constructor, we set the address of the contract deployer (`msg.sender`) as the admin.

### `modifier onlyAdmin()`

```solidity
modifier onlyAdmin() {
    require(msg.sender == admin, "Only admin can call this function");
    _;
}
```

#### Explanation:
- This is a modifier named `onlyAdmin`, which restricts access to functions or operations to the contract's admin.
- The underscore `_` indicates where the modified function's body will be inserted during execution.

### Admin Functions

#### Add Token

```solidity
function addToken(address _token) external onlyAdmin {
    tokens[_token] = true;
    emit TokenAdded(_token);
}
```

#### Explanation:
- The `addToken` function allows the admin to add a new ERC-20 token to the list of supported tokens for trading on the exchange.
- Only the admin can call this function (`onlyAdmin` modifier).
- Once the token is added, its address is stored in the `tokens` mapping, and an `TokenAdded` event is emitted.

#### Remove Token

```solidity
function removeToken(address _token) external onlyAdmin {
    delete tokens[_token];
    emit TokenRemoved(_token);
}
```

#### Explanation:
- The `removeToken` function allows the admin to remove an ERC-20 token from the list of supported tokens.
- Only the admin can call this function (`onlyAdmin` modifier).
- The token's address is removed from the `tokens` mapping, and a `TokenRemoved` event is emitted.

### Token Management

#### Deposit

```solidity
function deposit(address _token, uint256 _amount) external {
    require(tokens[_token], "Token not supported");
    IERC20(_token).transferFrom(msg.sender, address(this), _amount);
    balances[_token][msg.sender] += _amount;
}
```

#### Explanation:
- The `deposit` function allows users to deposit ERC-20 tokens into the exchange contract.
- It verifies that the token is supported by the exchange.
- It transfers tokens from the user's address to the exchange contract using the `transferFrom` function of the ERC-20 token contract.
- The deposited token amount is added to the user's balance in the `balances` mapping.

#### Withdraw

```solidity
function withdraw(address _token, uint256 _amount) external {
    require(balances[_token][msg.sender] >= _amount, "Insufficient balance");
    balances[_token][msg.sender] -= _amount;
    IERC20(_token).transfer(msg.sender, _amount);
}
```

#### Explanation:
- The `withdraw` function allows users to withdraw deposited tokens from the exchange contract back to their wallets.
- It verifies that the user has sufficient balance to withdraw.
- It transfers tokens from the exchange contract to the user's address using the `transfer` function of the ERC-20 token contract.
- The withdrawn token amount is subtracted from the user's balance in the `balances` mapping.

### Balances Management

#### Get Balance

```solidity
function getBalance(address _token, address _user) external view returns (uint256) {
    return balances[_token][_user];
}
```

#### Explanation:
- The `getBalance` function allows users to retrieve their token balance stored in the exchange contract.
- It takes the token address and user address as parameters and returns the corresponding balance from the `balances` mapping.

### Order Management

#### Create Order

```solidity
function createOrder(address _tokenGive, uint256 _amountGive, address _tokenGet, uint256 _amountGet) external {
        require(tokens[_tokenGive] && tokens[_tokenGet], "Tokens not supported");
        require(balances[_tokenGive][msg.sender] >= _amountGive, "Insufficient balance");

        Order memory newOrder = Order({
            tokenGive: _tokenGive,
            amountGive: _amountGive,
            tokenGet: _tokenGet,
            amountGet: _amountGet,
            creator: msg.sender
        });

        orders.push(newOrder);

        emit OrderCreated(_tokenGive, _amountGive, _tokenGet, _amountGet, msg.sender);
    }
```
### Explanation

- Allows users to create new orders on the decentralized exchange.
- Requires that both the giving and receiving tokens are supported on the exchange and that the user has enough balance to fulfill the order.
- Creates a new order with the provided token addresses, amounts, and the address of the user creating the order.
- Adds the new order to the `orders` array.
- Emits an `OrderCreated` event with the details of the newly created order.

#### Fill order

```solidity
 function fillOrder(uint256 _orderId) external {
        require(_orderId < orders.length, "Invalid order ID");
        Order memory order = orders[_orderId];

        require(balances[order.tokenGive][msg.sender] >= order.amountGive, "Insufficient balance");

        balances[order.tokenGive][msg.sender] -= order.amountGive;
        balances[order.tokenGet][msg.sender] += order.amountGet;

        emit OrderFilled(order.tokenGive, order.amountGive, order.tokenGet, order.amountGet, msg.sender);
    }
```
### Explanation

- Allows users to fill an existing order on the exchange specified by `_orderId`.
- Checks if the order ID is valid and within the range of available orders.
- Validates if the user has enough balance to fill the order.
- Transfers tokens from the user to the order creator as per the order details.
- Emits an `OrderFilled` event with the details of the filled order.

## Deploying and Interacting with the Contract

In this section, we'll guide you through the process of deploying and interacting with the decentralized exchange (DEX) smart contract using Remix, an online Solidity IDE. Remix provides a convenient interface for deploying and testing smart contracts directly from your web browser.

### Deployment

1. **Open Remix IDE**: Visit the [Remix website](https://remix.ethereum.org/) to launch the Remix IDE.
   ![em-remix-1](https://github.com/embolaweb3/DEX-tutorial/assets/163683760/b2fd6601-c41e-4bc7-8fb2-fdde6bc9ac6c)

2. **Create Contract**: Create a new file for your Solidity smart contract in Remix and paste the complete code.
![em-remix-2](https://github.com/embolaweb3/DEX-tutorial/assets/163683760/3de5bd4c-231c-4f10-b936-e127a1562499)
   
3. **Compile Contract**: Click on the "Solidity Compiler" tab in the sidebar and select the appropriate compiler version for your contract. Click "Compile" to compile your contract code.
![em-remix-3](https://github.com/embolaweb3/DEX-tutorial/assets/163683760/72ce2c43-5e20-4b7a-b4db-64a52eb88eea)

6. **Deploy Contract**: Once compiled successfully, switch to the "Deploy & Run Transactions" tab. Select the desired environment in our case, Injected Web3 from the dropdown menu and connect your CELO Alfajores wallet
![em-remix-4](https://github.com/embolaweb3/DEX-tutorial/assets/163683760/25405978-b65b-490c-ae95-ac0eaf05809f)

7. **Deploy Contract**: Click on the "Deploy" button to deploy to CELO Alfajores network.

   
9. **Confirm Deployment**: Confirm the deployment transaction in your connected wallet (e.g., MetaMask) if prompted. Wait for the transaction to be confirmed on the blockchain.

10. **Contract Address**: Once deployed, Remix will display the address of your deployed contract. Copy this address for future interactions.

### Interacting with the Contract

After deploying the contract, you can interact with it using Remix's built-in interface or through custom scripts and transactions.

1. **Read Functions**: Use the "Read" tab in Remix to call read-only functions of the deployed contract, such as querying token balances or checking order status.

2. **Write Functions**: Use the "Write" tab to call state-changing functions of the deployed contract, such as depositing tokens, creating orders, or filling orders.

3. **Transaction Execution**: Remix allows you to execute transactions directly from the interface, interacting with the contract in real-time. Confirm transactions in your connected wallet as needed.

4. **Debugging and Testing**: Use Remix's debugging and testing features to verify the behavior of your contract and ensure it functions as expected.

By following these steps, you can deploy your decentralized exchange smart contract to the Celo blockchain and interact with it seamlessly using Remix's intuitive interface.

## Conclusion

In this tutorial, we've explored the process of building a decentralized exchange (DEX) on the Celo blockchain using Solidity smart contracts. We've covered essential concepts such as token management, order creation and fulfillment, and trade execution, providing you with a solid foundation for creating your own DEX on Celo.

### Summary

We started by understanding the fundamentals of decentralized exchanges and the advantages of building on the Celo blockchain. We then delved into writing Solidity smart contracts to implement the core functionalities of our DEX, including token deposits and withdrawals, order management, and trade execution. Through step-by-step explanations and code examples, you gained insights into the inner workings of our decentralized exchange.

### Next Steps

Now that you've built your decentralized exchange prototype, there are several avenues you can explore to enhance its features and capabilities:

1. **User Interface Development**: Design and develop a user-friendly interface for interacting with your DEX, allowing users to trade tokens seamlessly.
2. **Liquidity Provision**: Implement liquidity pools and automated market makers (AMMs) to ensure sufficient liquidity for trading on your DEX.
3. **Security Audits**: Conduct comprehensive security audits to identify and mitigate potential vulnerabilities in your smart contracts.
4. **Community Engagement**: Engage with the Celo community to gather feedback, attract users, and foster adoption of your DEX.

By continuing to iterate and improve your decentralized exchange, you can contribute to the growth and development of decentralized finance (DeFi) on the Celo blockchain.

### Resources

- [Celo Developer Documentation](https://docs.celo.org/)
- [Remix Documentation](https://remix.ethereum.org/docs/)
- [Solidity Documentation](https://docs.soliditylang.org/)
- [OpenZeppelin Contracts](https://github.com/OpenZeppelin/openzeppelin-contracts)

These resources provide valuable information and tools to support your journey in building decentralized applications (dApps) on Celo and beyond.

Congratulations on completing this tutorial, and best of luck with your future endeavors in decentralized finance (DeFi)!

