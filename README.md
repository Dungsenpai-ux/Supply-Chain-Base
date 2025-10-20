# Blockchain Supply Chain Solution - Fair Trade Coconuts

**FAIR TRADE COCONUTS SUPPLY CHAIN**

A decentralized supply chain management system built on Ethereum blockchain for tracking coconuts from farm to consumer, ensuring transparency and fair trade practices.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Smart Contracts](#smart-contracts)
- [Testing](#testing)
- [UML Diagrams](#uml-diagrams)
- [Built With](#built-with)

## 🌟 Overview

This project implements a complete supply chain solution using blockchain technology to track fair trade coconuts through the entire supply chain lifecycle - from harvest to consumer purchase. The system ensures transparency, traceability, and authenticity of products.

## ✨ Features

- **Role-Based Access Control**: Four distinct roles (Farmer, Distributor, Retailer, Consumer)
- **Complete Product Lifecycle Tracking**: 8 states from Harvested to Purchased
- **Smart Contract Automation**: Automated state transitions and payment handling
- **Transparent Supply Chain**: Immutable record of product journey
- **Fair Trade Compliance**: Ensures fair payment distribution across supply chain actors

## 🏗️ Architecture

### Supply Chain Workflow

1. **Farmer** → Harvests, Processes, Packs, and Lists for Sale
2. **Distributor** → Purchases from Farmer and Ships
3. **Retailer** → Receives shipment from Distributor
4. **Consumer** → Purchases from Retailer

### UML Diagrams

- [Activity Diagram](documentation/Coconut-SupplyChain-Activity-Diagram.png)
- [Sequence Diagram](documentation/Coconut-SupplyChain-Sequence-Diagram.png)
- [State Diagram](documentation/Coconut-SupplyChain-State-Diagram.png)
- [Class Diagram](documentation/Coconut-SupplyChain-Class-Diagram.png)

## 📦 Prerequisites

Please ensure you have the following tools installed:

**Required:**
*   Node.js >= v16.0.0
*   npm >= 8.0.0
*   Truffle v5.11.5
*   Ganache CLI (latest)
*   Solidity ^0.8.19
*   MetaMask browser extension

**Dependencies:**
*   web3 ^4.3.0
*   @truffle/hdwallet-provider ^2.1.15
*   lite-server ^2.6.1

## 🚀 Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/Dungsenpai-ux/Supply-Chain-Base.git
cd Supply-Chain-Base
```

### Step 2: Install Dependencies

Install all required npm packages:

```bash
npm install
```

### Step 3: Start Ganache CLI

Open a terminal and launch Ganache with the following mnemonic:

```bash
ganache-cli -m "volume sense walk more oak rocket success treat rug boat pool soup"
```

**Test Accounts:**
```
Contract Owner: 0xfcf83e33d565a45411c7824d65084b435d5341b8
Farmer:         0xdc94ac22ec9eeddcf0fa46c0a2459b175864189c
Distributor:    0xbc0a52baff25eebc2c2a3d6ccb05db5e41f7da6e
Retailer:       0x59f48202795499a875c4d8eec510538d5365f1ce
Consumer:       0x335ca1a755db8bb13ddd6a6bb285eb91b3ec7b63
```

### Step 4: Compile Smart Contracts

In a separate terminal:

```bash
truffle compile
```

This will create smart contract artifacts in the `build/contracts` directory.

### Step 5: Migrate Contracts

Deploy smart contracts to the local blockchain:

```bash
truffle migrate
```

Or reset and redeploy:

```bash
npm run migrate:reset
```

### Step 6: Run Tests

Execute all test cases:

```bash
truffle test
```

All tests should pass successfully.

### Step 7: Launch DApp

Start the development server:

```bash
npm run dev
```

The DApp will be available at [http://localhost:3000](http://localhost:3000)

## 🎯 Usage

### Configure MetaMask

1. Install MetaMask browser extension
2. Import accounts using the mnemonic phrase or private keys from Ganache
3. Connect MetaMask to `http://localhost:8545`
4. Import the following accounts:
   - Contract Owner (accounts[0])
   - Farmer (accounts[1])
   - Distributor (accounts[2])
   - Retailer (accounts[3])
   - Consumer (accounts[4])

### Add Actors to Contract

As **Contract Owner**, add all actors to the contract:
1. Add Farmer role
2. Add Distributor role
3. Add Retailer role
4. Add Consumer role

### Execute Supply Chain Workflow

#### As Farmer (accounts[1]):
1. **Harvest** - Register new coconut batch
2. **Process** - Mark coconuts as processed
3. **Pack** - Pack coconuts for distribution
4. **For Sale** - List coconuts with price

#### As Distributor (accounts[2]):
5. **Buy** - Purchase from farmer (payment automatically transferred)

#### As Farmer (accounts[1]):
6. **Ship** - Ship to distributor

#### As Retailer (accounts[3]):
7. **Receive** - Confirm receipt of shipment

#### As Consumer (accounts[4]):
8. **Purchase** - Buy from retailer

## 📄 Smart Contracts

### Contract Structure

```
contracts/
├── coconutaccesscontrol/      # Role-based access control
│   ├── Roles.sol              # Library for managing roles
│   ├── FarmerRole.sol         # Farmer role management
│   ├── DistributorRole.sol    # Distributor role management
│   ├── RetailerRole.sol       # Retailer role management
│   └── ConsumerRole.sol       # Consumer role management
├── coconutcore/               # Core ownership functionality
│   └── Ownable.sol            # Ownership and transfer control
└── coconutbase/               # Main supply chain logic
    └── SupplyChain.sol        # Complete supply chain implementation
```

### Key Contract Features

- **SupplyChain.sol**: Main contract managing the entire supply chain lifecycle
- **Role-based Access**: Separate contracts for each supply chain actor
- **State Management**: 8 distinct states tracking product journey
- **Payment Automation**: Automatic fund transfer between parties
- **Event Logging**: Complete audit trail of all transactions

### Product States

1. `Harvested` - Initial state after harvest
2. `Processed` - Coconuts processed
3. `Packed` - Ready for distribution
4. `ForSale` - Listed for sale
5. `Sold` - Purchased by distributor
6. `Shipped` - In transit
7. `Received` - Received by retailer
8. `Purchased` - Final purchase by consumer

## 🧪 Testing

The project includes comprehensive test coverage:

```bash
npm test
```

Tests verify:
- Role assignment and permissions
- State transitions
- Payment handling
- Access control
- Complete workflow execution

## 🛠️ Built With

* **[Ethereum](https://www.ethereum.org/)** - Decentralized blockchain platform
* **[Solidity](https://soliditylang.org/)** - Smart contract programming language
* **[Truffle](https://trufflesuite.com/)** - Development framework for Ethereum
* **[Ganache](https://trufflesuite.com/ganache/)** - Personal blockchain for development
* **[Web3.js](https://web3js.readthedocs.io/)** - Ethereum JavaScript API
* **[MetaMask](https://metamask.io/)** - Ethereum wallet and gateway
* **[Node.js](https://nodejs.org/)** - JavaScript runtime
* **[Lite-server](https://github.com/johnpapa/lite-server)** - Lightweight development server

## 📝 Project Structure

```
Suppy-Chain-Basic-Architecture/
├── contracts/              # Smart contracts
├── migrations/             # Deployment scripts
├── test/                   # Test files
├── src/                    # Frontend source
│   └── js/                 # JavaScript files
├── build/                  # Compiled contracts
├── documentation/          # UML diagrams
├── images/                 # Project images
├── truffle-config.js       # Truffle configuration
├── package.json            # Project dependencies
└── README.md              # Project documentation
```

## 📊 Libraries Used

- **Roles.sol**: Library for managing addresses assigned to specific roles
- **Ownable.sol**: Provides basic authorization control and ownership management

## 🌐 Network Configuration

The project is configured for:
- **Local Development**: Ganache CLI (127.0.0.1:8545)
- **Test Network**: Configurable for Rinkeby/Sepolia

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📜 License

This project is licensed under the MIT License.

## 👨‍💻 Author

**Dungsenpai-ux**
- GitHub: [@Dungsenpai-ux](https://github.com/Dungsenpai-ux)
- Repository: [Supply-Chain-Base](https://github.com/Dungsenpai-ux/Supply-Chain-Base)

## 🙏 Acknowledgments

* Solidity community
* Truffle Suite team
* Ethereum Foundation
* OpenZeppelin for security best practices
* Udacity Blockchain Nanodegree Program

## 📞 Support

For issues and questions:
- Open an issue on [GitHub](https://github.com/Dungsenpai-ux/Supply-Chain-Base/issues)
- Check documentation in `/documentation` folder

---

**Note**: This is an educational project demonstrating blockchain supply chain implementation. For production use, additional security audits and testing are recommended.