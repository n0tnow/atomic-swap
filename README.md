
![ChatGPT Image 2 Haz 2025 19_55_40](https://github.com/user-attachments/assets/2689c61a-0c44-4937-991e-f09336da4f8f)


# Atomic Swap Contract 🚀

A smart contract built on the **Soroban** platform (Stellar Testnet) that enables **trustless atomic swaps** of tokens between two parties.

---

## 🌟 Overview

This contract facilitates **atomic** (indivisible) token exchanges between two different parties on the Stellar blockchain.  
The key feature is that parties don't need to know or trust each other, and their signatures can be matched off-chain.

✅ Swap either completes entirely or fails completely  
✅ Eliminates counterparty risk  
✅ Supports minimum price protection & automatic refunds

---

## 🔗 Deployed Contract

- **Stellar Testnet Contract ID:*CA2TSFJQBVX6D2QNE5T7KFWKJWZB2MNHCOASRBRQYJ7YC7TSGCKBQWDB*  


- **View on Stellar Expert:**  
[View Contract on Stellar Expert](https://stellar.expert/explorer/testnet/contract/CA2TSFJQBVX6D2QNE5T7KFWKJWZB2MNHCOASRBRQYJ7YC7TSGCKBQWDB)

---

## 🛠️ Contract Functionality

### 🔄 `swap` Function

```rust
pub fn swap(
  env: Env,
  a: Address,
  b: Address,
  token_a: Address,
  token_b: Address,
  amount_a: i128,
  min_b_for_a: i128,
  amount_b: i128,
  min_a_for_b: i128,
)

Parameters:
env: Soroban environment

a and b: Addresses of the two parties involved in the swap

token_a and token_b: Addresses of the tokens to be exchanged

amount_a: Amount of token_a that user A is willing to give

min_b_for_a: Minimum amount of token_b that user A expects in return

amount_b: Amount of token_b that user B is willing to give

min_a_for_b: Minimum amount of token_a that user B expects in return
```

# ⚙️ How It Works
1️⃣ Precondition Verification:

Ensures amount_b ≥ min_b_for_a (user A’s minimum expectation)

Ensures amount_a ≥ min_a_for_b (user B’s minimum expectation)

2️⃣ Authorization:

Requires authorization from both parties

Signatures can be matched off-chain

3️⃣ Atomic Swap Execution:

Transfers token_a from user A to user B

Transfers token_b from user B to user A

Automatically refunds any excess tokens


# 📦 Build and Deploy

## 🛠️ Build the Contract

soroban contract build

🚀 Deploy to Stellar Testnet

stellar network use testnet

stellar contract deploy \
  --wasm target/wasm32-unknown-unknown/release/soroban_atomic_swap.wasm \
  --source alice \
  --network testnet
⚠️ Security Considerations

Ensures atomic execution: no partial swaps

Authorization required from both parties

Minimum price protection to avoid unfair trades

Trustless intermediary, no 3rd party required

## 💡 How to Use

1️⃣ Clone this repo and build the project:

git clone https://github.com/n0tnow/atomic-swap.git
cd atomic-swap/soroban-atomic-swap
soroban contract build
