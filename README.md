# PIXELZX-Chain

PIXELZX-Chain is a Proof-of-Work (PoW) blockchain based on a fork of go-ethereum (geth), with PIXELZX (PZX) as its native token. It supports Ethereum Virtual Machine (EVM) for smart contract execution, enabling decentralized applications (dApps) with PZX as the primary currency for transactions and mining rewards.

## Features
- **Native Token**: PZX is the native cryptocurrency used for transaction fees and mining rewards.
- **EVM Compatibility**: Supports Solidity smart contracts for building dApps.
- **Proof-of-Work**: Utilizes Ethash (or customizable SHA-256) for consensus.
- **Customizable**: Easily extendable for specific use cases like DeFi, NFTs, or gaming.

## Prerequisites
- Go (version 1.18 or later)
- Git
- Make (for building the project)
- A compatible operating system (Linux, macOS, or Windows with WSL)

## Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Alex110709/PIXELZX-Chain.git
   cd PIXELZX-Chain
   ```

2. **Install Dependencies**:
   ```bash
   go mod tidy
   ```

3. **Build the Project**:
   ```bash
   make geth
   ```

## Usage
### Initialize the Chain
Initialize the blockchain with the genesis block containing the initial PZX supply:
```bash
./build/bin/geth --datadir ./pzxdata init genesis.json
```

### Run a Node
Start a PIXELZX-Chain node:
```bash
./build/bin/geth --datadir ./pzxdata --networkid 12345
```

### Check PZX Balance
Use the geth console to check the balance of an address:
```bash
./build/bin/geth --datadir ./pzxdata attach
> web3.fromWei(eth.getBalance("0xYourWalletAddressHere"), "PZX")
```

### Mining
To start mining and earn PZX rewards:
```bash
./build/bin/geth --datadir ./pzxdata --networkid 12345 --mine --miner.etherbase=0xYourWalletAddressHere
```

### Deploy Smart Contracts
Deploy Solidity smart contracts using tools like Remix or Hardhat, targeting the PIXELZX-Chain network (chain ID: 12345).

## PZX Token
- **Token Name**: PixelZX
- **Symbol**: PZX
- **Unit**: 1 PZX = 10^18 wei
- **Initial Supply**: 1,000,000 PZX allocated in `genesis.json`
- **Mining Reward**: 2 PZX per block (configurable in `miner/miner.go`)
- **Gas Fees**: Paid in PZX, with a minimum gas price of 1 Gwei

## Configuration
- **Genesis File**: `genesis.json` defines the chain ID (12345), initial PZX supply, and Ethash PoW settings.
- **Protocol Parameters**: `params/protocol_params.go` includes PZX unit definitions and token metadata.
- **Mining Rewards**: Configured in `miner/miner.go`.

## Contributing
We welcome contributions to PIXELZX-Chain! To contribute:
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-name`).
3. Commit your changes (`git commit -m "Add feature"`).
4. Push to your branch (`git push origin feature-name`).
5. Open a Pull Request on GitHub.

**Note**: Avoid force-pushing (`git push -f`) to the `main` branch to prevent overwriting collaborative work.

## License
This project is licensed under the GNU Lesser General Public License v3.0, as inherited from go-ethereum. See [LICENSE](LICENSE) for details.

## Contact
For issues or questions, open an issue on [GitHub](https://github.com/Alex110709/PIXELZX-Chain) or contact the project maintainer.
