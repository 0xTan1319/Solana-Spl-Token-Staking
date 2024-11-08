# Solana SPL Token Staking Smart Contract

This project implements a staking smart contract on the Solana blockchain using Anchor. The contract allows users to stake and unstake SPL tokens, fund the staking pool with rewards, and claim earned rewards. It features a basic staking mechanism, with reward accrual and distribution based on the amount of time tokens are staked.

## Features

- **Initialize Staking Pool**: Creates a new staking pool that tracks total staked tokens, rewards, and other related information.
- **Fund Staking Pool**: Allows an owner to fund the staking pool with SPL tokens that will be used for rewards.
- **Stake Tokens**: Users can stake their SPL tokens into the staking pool, which are transferred to the vault.
- **Unstake Tokens**: Users can unstake their tokens and claim accrued rewards.
- **Claim Rewards**: Users can claim their earned rewards without unstaking their principal amount.
- **Reward Accrual**: Rewards are calculated based on the amount of time tokens have been staked.

## Requirements

- **Rust**: Make sure you have Rust installed on your machine.
- **Solana CLI**: You need the Solana CLI to interact with the Solana blockchain.
- **Anchor**: Install Anchor framework to develop on Solana using the Rust language.
  
  ```bash
  $ npm install -g @project-serum/anchor-cli
  ```
## Getting Started

To get started with this smart contract, follow these steps:

1. Clone the Repository
  Clone the repository to your local machine:

```bash
  $ git clone https://github.com/your-username/solana-spl-token-staking-smart-contract.git
  $ cd solana-spl-token-staking-smart-contract
```

2. Install Dependencies
Install the required dependencies using Anchor:

```bash
$ anchor build
```

3. Deploy the Contract
Deploy the staking contract to a Solana cluster (Devnet or Mainnet):

```bash
$ anchor deploy
```

4. Interact with the Smart Contract
You can interact with the smart contract by invoking the following functions using Anchor scripts or directly via a client-side application.

Initialize the staking pool
Fund the pool with tokens
Stake tokens into the pool
Unstake tokens and claim rewards
Claim rewards from the pool
Contract Overview
initialize (Function)
Initializes the staking pool with the provided owner's address and staking token mint. Sets up the reward parameters and initial state.

fund (Function)
Funds the staking pool by transferring tokens from the funder's associated token account (ATA) to the vault, updating the reward pool.

stake (Function)
Transfers tokens from the user's wallet to the staking pool's vault, updating the user's staked amount and the pool's total staked amount.

unstake (Function)
Unstakes tokens and rewards from the staking pool back to the user, updating the staking pool and user's state.

claim (Function)
Claims earned rewards from the staking pool, leaving the principal staked tokens in the pool.

Data Structures
StakingPool: Contains the staking pool's owner, total staked amount, total reward amount, and the reward rate.
StakerInfo: Stores information for each staker, such as staked amount, earned rewards, and the timestamp of the last stake.
Example Usage
Initialize Staking Pool

```bash
$ anchor invoke -u <pool_creator_key> initialize
```

Stake Tokens

```bash
$ anchor invoke -u <user_key> stake --amount <amount_in_tokens>
Unstake Tokens
```

```bash
$ anchor invoke -u <user_key> unstake --amount <amount_in_tokens>
```

Claim Rewards
```bash
$ anchor invoke -u <user_key> claim
```

### Error Handling
The contract has built-in error handling for common situations:

InsufficientStake: Attempt to unstake more than the staked amount.
ZeroStake: Attempt to stake 0 tokens.
NoStake: Attempt to unstake when no tokens are staked.

### License
This project is licensed under the MIT License - see the LICENSE file for details.

### Acknowledgments
Solana
Anchor Framework
Rust
markdown
Copy code

### Key Points of the README:
- **Overview** of the project
- **Features** that the smart contract supports
- **Installation instructions** for dependencies and environment setup
- **Deployment instructions** to Solana
- **Usage examples** for common functions
- **Contract overview** detailing each function's purpose
