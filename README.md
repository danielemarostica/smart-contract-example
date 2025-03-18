## Smart Contract Example

I created this simple project to showcase how to deploy an EVM compatible Smart Contract with the [Mia-Platform Console](https://mia-platform.eu/platform/console/)

Under the hood, this Smart Contract is bilt using [Foundry](https://book.getfoundry.sh): a fast, portable and modular toolkit for Ethereum application development written in Rust.  
Foundry consists of:

- **Forge**: Ethereum testing framework (like Truffle, Hardhat and DappTools).
- **Cast**: Swiss army knife for interacting with EVM smart contracts, sending transactions and getting chain data.
- **Anvil**: Local Ethereum node, akin to Ganache, Hardhat Network.
- **Chisel**: Fast, utilitarian, and verbose solidity REPL.

## Usage

### Build

```shell
forge build
```

### Test

```shell
forge test
```

### Format

```shell
forge fmt
```

### Gas Snapshots

```shell
forge snapshot
```

### Anvil

Use Anvil to run an Local Ethereum node for testing purposes
By default this node runs on `localhost:8545`

```shell
anvil
```

### Deploy

```shell
forge script script/Counter.s.sol:CounterScript --rpc-url <node_rpc_url> --private-key <your_private_key> --broadcast
```

Here some RPC-URLs:

- Local Anvil: `localhost:8545`
- "Amoy" the Polygon testnet: `https://rpc-amoy.polygon.technology/`

### Cast

Use cast to interact with the Ethereum Node

```shell
cast <subcommand>
```

Eg: retrieve the counter from the "Counter" Smart Contract deployed on Amoy testnet:

```shell
cast call 0x673c16401AD6960655548B049Db56a75bbBcef38 "retrieve()" --rpc-url https://rpc-amoy.polygon.technology/
```

Eg: set the counter of the "Counter" Smart Contract deployed on Amoy testnet to a custom value:

```shell
cast send 0x673c16401AD6960655548B049Db56a75bbBcef38 "store(uint256)" 42 --rpc-url https://rpc-amoy.polygon.technology/ --private-key <your_private_key>
```
