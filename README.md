# EventChain  
Decentralized Event Ticketing App

[![HiDevs GitAgent Passport](https://img.shields.io/badge/HiDevs-GitAgent%20Passport-blueviolet?style=flat-square)](https://app.hidevs.xyz/passport/submit)
[![OpenGAP](https://img.shields.io/badge/OpenGAP-v0.1.0-blue?style=flat-square)](https://github.com/open-gitagent/opengap)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Agent](https://img.shields.io/badge/agent-eventchain--agent-orange?style=flat-square)](agent.yaml)

EventChain is an autonomous, decentralized blockchain-based event ticketing platform and intelligence agent that leverages ERC-721 NFTs on Polygon, smart contracts, and a Flutter mobile architecture to eliminate ticket fraud, ensure transparent ownership, and enable secure event entry verification.

---

## 1. What is EventChain ?

EventChain is a decentralized event ticketing system where event tickets are issued as **ERC-721 NFTs** on the **Polygon blockchain**. Each ticket is uniquely owned, verifiable on-chain, and protected from duplication or manipulation.

### Key Goals
- Eliminate ticket fraud and duplication  
- Provide transparent, on-chain ticket ownership  
- Enable secure peer-to-peer ticket transfers  
- Ensure trustless event entry verification  
- Reduce reliance on centralized ticketing platforms  

### Core Features
- Blockchain-backed NFT tickets (ERC-721)  
- Flutter-based mobile application  
- Firebase-powered authentication and off-chain storage  
- QR-code based ticket validation  
- Organizer dashboard and entry scanner  
- IPFS-based NFT metadata storage  

---

## 2. Setting up Flutter on Your Device ?

### Prerequisites
- Windows / macOS / Linux
- Git
- Android Studio or VS Code

#### Essential Versions

##### Mobile Application Environment

- Flutter SDK: ^3.27.0
- Dart SDK: 3.6.0 (bundled with Flutter 3.27.x)

##### Android Development Configuration

- Compile SDK Version: API level 35 (Android 15 - recommended)
- Target SDK Version: API level 35 (Android 15 - recommended)
- Android Studio: Flamingo or later

##### Java & Build Tools

- Java Development Kit (JDK): 17 (recommended) or 21

##### Backend Services

- Firebase Authentication: Latest
- Cloud Firestore: Latest

##### Blockchain Configuration

- Blockchain Network: Polygon PoS (Mumbai Testnet)
- Smart Contract Language: Solidity ^0.8.20
- Token Standard: ERC-721

##### Blockchain Development Tooling

- Node.js: 18.x LTS
- Hardhat: ^2.19 (2.19.1 - recommended)
- ethers.js: ^6.x (6.0.0 - recommended)
- Decentralized Storage -IPFS (Pinata): Latest

##### Required Flutter Dependencies

flutter_riverpod: ^2.5.1-
https://pub.dev/packages/flutter_riverpod

firebase_core: ^3.6.0-
https://pub.dev/packages/firebase_core

cloud_firestore: ^5.4.0-
https://pub.dev/packages/cloud_firestore

go_router: ^14.2.0-
https://pub.dev/packages/go_router


### Flutter Installation Steps

1. Download Flutter SDK  
   https://docs.flutter.dev/get-started/install

2. Extract the SDK and add Flutter to PATH

   ```bash
   export PATH="$PATH:`pwd`/flutter/bin"

3. Verify Flutter installation

    ```bash
    flutter doctor

4. Install required platform tools

- Android Studio (Android SDK + Emulator)
- Xcode (macOS users for iOS)

5. Accept Android licenses

    ```bash
    flutter doctor --android-licenses

Once all checks pass, Flutter is ready to use.

---

## 3. Setting up this Project and Requirements ?

### 3.1 Technology Stack
| Layer                  | Technology                |
| ---------------------- | ------------------------- |
| Mobile App             | Flutter                   |
| Language               | Dart                      |
| Authentication         | Firebase Authentication   |
| Off-chain Database     | Firebase Firestore        |
| Blockchain Network     | Polygon                   |
| Smart Contracts        | Solidity (ERC-721)        |
| Blockchain Dev         | Hardhat                   |
| Blockchain Interaction | ethers.js (flutter_ether) |
| NFT Metadata           | IPFS (Pinata)             |

### 3.2 Project Structure

```text
lib/
├── main.dart
├── app.dart
├── models/
│   ├── user.dart
│   ├── event.dart
│   └── ticket.dart
├── screens/
│   ├── auth/
│   ├── home/
│   ├── event/
│   ├── tickets/
│   ├── profile/
│   └── scanner/
├── services/
│   ├── firebase_service.dart
│   ├── blockchain_service.dart
│   └── ipfs_service.dart
├── providers/
└── utils/

contracts/
├── EventTicket.sol

scripts/
├── deploy.js

test/
├── EventTicket.test.js
```


### 3.3 Firebase Setup

1. Create a Firebase project
2. Enable Firebase Authentication
3. Enable Firestore Database
4. Download google-services.json / GoogleService-Info.plist
5. Configure Firebase in Flutter
6. Initialize Firebase in main.dart

Firebase is used only for:
- User authentication
- Event listings and metadata
- Wallet-to-user mappings

Ticket ownership and validation are handled only on-chain.

### 3.4 Smart Contract Setup
1. Install dependencies

    ```bash
    npm install

2. Compile smart contracts

    ```bash
    npx hardhat compile

3. Deploy contracts to Polygon (Testnet/Mainnet)

    ```bash
    npx hardhat run scripts/deploy.js --network polygonMumbai

4. Save deployed contract address in Flutter configuration

### 3.5 Running the Flutter Application

    flutter pub get
    flutter run

---

## 4. Contributors' Guide

We welcome contributions from developers, designers, and blockchain enthusiasts.

Before contributing, please read the official contribution documents to ensure a smooth review process:

- 📘 Contribution Guide: CONTRIBUTING.md
- 📄 Pull Request Template: PULL_REQUEST_TEMPLATE.md

These documents explain:

- Coding standards and best practices
- Branching and commit message conventions
- Testing and documentation requirements
- Pull request submission and review process

### How to Contribute

1. Fork the repository
2. Create a feature branch

    ```bash
    git checkout -b feature/your-feature-name

3. Make your changes following the guidelines in CONTRIBUTING.md
4. Commit your changes with clear and meaningful messages
5. Push the branch to your fork
6. Open a Pull Request using the provided PR template

>⚠️ Pull requests that do not follow the contribution guidelines or the **PULL REQUEST template** may be requested for changes or closed.


### Areas Open for Contribution

- UI/UX enhancements
- Smart contract optimization
- Security audits
- QR validation improvements
- Wallet integrations
- Analytics and reporting tools

### License

This project is licensed under the MIT License.

### Contact

For project-related queries or issues, please reach out via **Discord**.

 
> - Use the designated Discord channels for discussions and support  
> - Avoid unnecessary direct messages (DMs) and random pings  

EventChain — Redefining Event Ticketing with Blockchain.

---

## 🛂 HiDevs GitAgent Passport Submission

- **Portal**: [HiDevs GitAgent Passport](https://app.hidevs.xyz/passport/submit)
- **Repository**: `Chithra582/EventChain`
- **Category**: **Finance** (or **Retail & e-commerce**)

