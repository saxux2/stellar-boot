<img width="1919" height="1079" alt="Screenshot 2026-04-13 140121" src="https://github.com/user-attachments/assets/88b76e89-99ce-48ee-8e50-7eea8d30718b" />

# Stellar Boot: Soroban SimpleStorage Contract

This repository contains a simple Soroban smart contract for the Stellar blockchain, demonstrating basic storage and retrieval functionality. It is structured for easy extension and integration into larger Stellar-based projects.

## Project Structure
https://stellar.expert/explorer/testnet/contract/CDXM3O5ZXZVDSYZCCBDNPLG55BLYY26UB75WTK4VNMH4WDR6DFBFA35C
```
.
├── contracts
│   └── contract
│       ├── src
│       │   ├── lib.rs      # Main contract logic
│       │   └── test.rs     # Unit tests for the contract
│       ├── Cargo.toml      # Contract-specific dependencies
│       └── Makefile        # Build/test helpers
├── Cargo.toml              # Workspace configuration
├── README.md               # Project documentation
└── .gitignore
```

## Contract Overview

The `SimpleStorage` contract allows you to store and retrieve a single `u32` value on-chain.

- `set(env: Env, value: u32)`: Stores the provided value.
- `get(env: Env) -> u32`: Retrieves the stored value (returns 0 if unset).

### Example Usage

```rust
let env = Env::default();
SimpleStorage::set(env.clone(), 42);
let value = SimpleStorage::get(env);
assert_eq!(value, 42);
```

## Building and Testing

Navigate to the contract directory and use the provided Makefile or Cargo commands:

```sh
cd contracts/contract
make build      # Build the contract
make test       # Run tests
```

Or use Cargo directly:

```sh
cargo build --release
cargo test
```

## Extending the Project
- Add new contracts in the `contracts/` directory, each with its own folder.
- Update the workspace `Cargo.toml` to include new contracts.

## Requirements
- Rust (latest stable)
- [Soroban CLI](https://soroban.stellar.org/docs/getting-started/installation)

## License
MIT
