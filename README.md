# Kairo Wallet

<div align="center">

**A Secure, Lightweight, and Open-Source EVM-Compatible Blockchain Wallet**

*Built with Flutter for iOS, Android, and beyond*

[Features](#features) • [Security](#security) • [Supported Networks](#supported-networks) • [Installation](#installation) • [Documentation](#documentation)

</div>

---

## Overview

Kairo Wallet is a next-generation cryptocurrency wallet designed for the Ethereum ecosystem and all EVM-compatible blockchains. Built with Flutter for cross-platform compatibility, Kairo provides a secure, user-friendly interface for managing digital assets across Layer 1 (L1) and Layer 2 (L2) networks.

### Why Kairo?

- **Universal EVM Support**: Compatible with Ethereum and all EVM-based chains
- **Multi-Layer Architecture**: Seamless support for both L1 and L2 networks
- **Security First**: Military-grade encryption with local key storage
- **Cross-Platform**: Native performance on iOS and Android
- **Open Source**: Transparent, auditable, and community-driven
- **Developer Friendly**: Clean architecture and extensible design

---

## Features

### Core Capabilities

#### 🔐 Security & Privacy
- **Local Key Encryption**: Private keys encrypted and stored securely on device
- **Hardware-Backed Security**: Utilizes iOS Keychain and Android Keystore
- **No Server Dependencies**: Fully decentralized - your keys never leave your device
- **BIP39/BIP44 Standard**: Industry-standard HD wallet implementation
- **Biometric Authentication**: Face ID, Touch ID, and fingerprint support

#### 💎 Asset Management
- **Multi-Chain Support**: Manage assets across multiple EVM chains simultaneously
- **Token Discovery**: Automatic detection of ERC-20 tokens
- **NFT Gallery**: View and manage your NFT collections (ERC-721, ERC-1155)
- **Transaction History**: Complete on-chain activity tracking
- **Custom Tokens**: Add any ERC-20 token manually

#### ⚡ Network Support
- **Layer 1 Networks**: Ethereum Mainnet and EVM-compatible L1 chains
- **Layer 2 Networks**: Optimism, Arbitrum, Polygon, Base, and more
- **Custom RPC**: Connect to any EVM-compatible network
- **Network Switching**: Seamless switching between networks
- **Gas Optimization**: Smart gas fee estimation and customization

#### 🚀 User Experience
- **Intuitive Interface**: Clean, modern design built with Flutter
- **Fast Performance**: Native compilation for optimal speed
- **QR Code Support**: Easy address sharing and scanning
- **Multi-Language**: Internationalization ready
- **Dark Mode**: System-adaptive theme support

---

## Security

Security is the foundation of Kairo Wallet. We implement industry best practices to protect your assets:

### Encryption Architecture

```
User Passphrase
    ↓
PBKDF2 Key Derivation
    ↓
AES-256-GCM Encryption
    ↓
Encrypted Private Key → Secure Storage (Keychain/Keystore)
```

### Key Security Features

1. **Local-Only Storage**: Private keys never transmitted or stored on servers
2. **Military-Grade Encryption**: AES-256-GCM with authenticated encryption
3. **Key Derivation**: PBKDF2 with high iteration count for brute-force resistance
4. **Secure Enclaves**: iOS Keychain and Android Hardware-Backed Keystore integration
5. **Memory Protection**: Sensitive data cleared from memory after use
6. **No Analytics**: No tracking, no telemetry, complete privacy

### Security Best Practices

- Always backup your recovery phrase securely offline
- Use strong passphrases with biometric authentication
- Verify contract addresses before transactions
- Keep your device OS updated
- Never share your private keys or recovery phrase

---

## Supported Networks

### Layer 1 (L1) Networks
- Ethereum Mainnet
- Binance Smart Chain (BSC)
- Avalanche C-Chain
- Fantom Opera
- Any EVM-compatible L1 chain

### Layer 2 (L2) Networks
- Optimism
- Arbitrum One
- Arbitrum Nova
- Polygon (formerly Matic)
- Base
- zkSync Era
- Linea
- Scroll
- Any EVM-compatible L2 solution

### Custom Networks
Kairo supports adding custom RPC endpoints for:
- Testnets (Goerli, Sepolia, Mumbai, etc.)
- Private networks
- Development environments
- Any EVM-compatible network

---

## Installation

### Prerequisites
- Flutter SDK 3.32 or higher
- Dart SDK 3.0 or higher
- Android Studio / Xcode (for mobile development)
- Git

### Build from Source

```bash
# Clone the repository
git clone https://github.com/yourusername/kairo.git
cd kairo

# Install dependencies
flutter pub get

# Run code generation (if applicable)
flutter pub run build_runner build

# Run on device/emulator
flutter run

# Build for production
flutter build apk --release          # Android
flutter build ios --release          # iOS
flutter build appbundle --release    # Android App Bundle
```

### Development Setup

```bash
# Run in debug mode
flutter run --debug

# Run with hot reload
flutter run --hot

# Run tests
flutter test

# Check code quality
flutter analyze
```

---

## Architecture

### Technology Stack

- **Framework**: Flutter 3.32+
- **Language**: Dart 3.0+
- **Blockchain**: Ethereum / EVM-compatible chains
- **Encryption**: AES-256-GCM with PBKDF2
- **Storage**: Secure platform storage (Keychain/Keystore)

### Project Structure

```
kairo/
├── lib/
│   ├── core/                 # Core functionality
│   │   ├── crypto/          # Cryptography and key management
│   │   ├── storage/         # Secure storage implementations
│   │   └── network/         # Network layer and RPC
│   ├── features/            # Feature modules
│   │   ├── wallet/          # Wallet management
│   │   ├── transactions/    # Transaction handling
│   │   ├── tokens/          # Token management
│   │   └── settings/        # App settings
│   ├── shared/              # Shared components
│   │   ├── widgets/         # Reusable UI components
│   │   ├── models/          # Data models
│   │   └── utils/           # Utility functions
│   └── main.dart            # Application entry point
├── test/                    # Unit and widget tests
├── android/                 # Android-specific code
├── ios/                     # iOS-specific code
└── pubspec.yaml            # Dependencies and metadata
```

### Key Dependencies

- **web3dart**: Ethereum client library
- **bip39**: Mnemonic phrase generation
- **ed25519_hd_key**: HD key derivation
- **flutter_secure_storage**: Secure platform storage
- **local_auth**: Biometric authentication
- **http**: Network requests
- **provider/riverpod**: State management

---

## Usage

### Creating a New Wallet

1. Launch Kairo Wallet
2. Select "Create New Wallet"
3. Set a strong passphrase
4. **IMPORTANT**: Write down your 12/24-word recovery phrase
5. Verify your recovery phrase
6. Enable biometric authentication (optional)

### Importing an Existing Wallet

1. Select "Import Wallet"
2. Enter your recovery phrase or private key
3. Set a new passphrase
4. Complete setup

### Sending Transactions

1. Select the network and token
2. Tap "Send"
3. Enter recipient address (or scan QR code)
4. Enter amount and review gas fees
5. Confirm with passphrase or biometric
6. Transaction submitted to blockchain

### Managing Networks

1. Go to Settings > Networks
2. Select from pre-configured networks or add custom RPC
3. Enter network details:
   - Network Name
   - RPC URL
   - Chain ID
   - Currency Symbol
   - Block Explorer URL (optional)

---

## Development

### Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Building Features

```bash
# Create new feature module
mkdir -p lib/features/your_feature

# Add tests
mkdir -p test/features/your_feature

# Run tests
flutter test test/features/your_feature
```

### Code Style

- Follow Dart style guide
- Use `flutter analyze` before committing
- Write tests for new features
- Document public APIs

### Testing

```bash
# Run all tests
flutter test

# Run with coverage
flutter test --coverage

# Run specific test file
flutter test test/core/crypto/encryption_test.dart
```

---

## Security Disclosure

If you discover a security vulnerability, please email security@kairo-wallet.io instead of using the issue tracker. We take security seriously and will respond promptly.

---

## Roadmap

### Current Version (v1.0)
- ✅ EVM wallet core functionality
- ✅ L1/L2 network support
- ✅ Secure key management
- ✅ Token and NFT support

### Upcoming Features
- 🔄 WalletConnect integration
- 🔄 Hardware wallet support (Ledger, Trezor)
- 🔄 DApp browser
- 🔄 Multi-signature wallets
- 🔄 Staking support
- 🔄 DeFi protocol integration
- 🔄 Enhanced NFT features

---

## FAQ

**Q: Is Kairo Wallet safe to use?**
A: Yes. Kairo implements industry-standard encryption and stores all keys locally on your device. However, you are responsible for securing your recovery phrase.

**Q: Can I use Kairo with other wallets?**
A: Yes. Kairo uses standard BIP39/BIP44, so you can import your recovery phrase from other wallets.

**Q: Does Kairo collect any data?**
A: No. Kairo is completely privacy-focused with no analytics or tracking.

**Q: What networks are supported?**
A: All EVM-compatible networks including Ethereum L1 and major L2s like Arbitrum, Optimism, and Polygon.

**Q: Is there a desktop version?**
A: Currently, Kairo is mobile-first (iOS/Android), but desktop support may be added in the future.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

Built with:
- [Flutter](https://flutter.dev) - Google's UI toolkit
- [web3dart](https://pub.dev/packages/web3dart) - Ethereum library for Dart
- [EVM Community](https://ethereum.org) - The Ethereum ecosystem

---

<div align="center">

**Made with ❤️ for the decentralized future**

*Kairo Wallet - Your keys, your crypto, your control*

</div>
