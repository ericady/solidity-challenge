# 1) Challenge completed
#### Project config
- Solidity version 0.8.17
- Hardhat
- Typescript
#### Requirements
- Only the team can deposit rewards.
- Deposited rewards go to the pool of users, not to individual users.
- Users should be able to withdraw their deposits along with their share of rewards considering the time when they deposited.

All requirements completed.

# 2) Unit tests
#### All unit tests passed.
```
  ETHPool
    Team priviledged function
      ✔ Only owner can set team wallet (49ms)
      ✔ Only team wallet can deposit rewards
      ✔ Team should be able to charge rewards after 1 week
    Stake / Unstake
      ✔ users should be able to stake eth in the pool
      ✔ should be able to get pending rewards
      ✔ should be able to unstake staked balance with rewards
    More testing scenarios
      ✔ A stake 100, B stake 300, T deposit 200 rewards => A withdraw 25%, B withdraw 75% rewards (58ms)
      ✔ A stake 100, T deposit 200 rewards, B stake 300 => A withdraw 100%, B withdraw 0% rewards (58ms)
      ✔ A stake 100, T deposit 200 rewards, A stake 300 again => A withdraw 100% (58ms)
      ✔ A stake 100, A stake 300 again, T deposit 200 rewards  => A withdraw 100% (41ms)
      ✔ A stake 100, B stake 200, A stake 200 again, T deposit 200 rewards  => A withdraw 60%, B withdraw 40% (59ms)
      ✔ A - 100, B - 300, T - 200 | A - 100, T - 200 | A - 300, B - 100, T - 200  => A rewards 400, B withdraw 200 (86ms)
```
#### Code coverage rate
| File           | % Stmts    | % Branch   | % Funcs    | % Lines    | Uncovered Lines  |
| -------------- | ---------- | ---------- | ---------- | ---------- | ---------------- |
| contracts/     | 100        | 91.67      | 100        | 100        |                  |
| ETHPool.sol    | 100        | 91.67      | 100        | 100        |                  |
| -------------- | ---------- | ---------- | ---------- | ---------- | ---------------- |
| All files      | 100        | 91.67      | 100        | 100        |                  |
| -------------- | ---------- | ---------- | ---------- | ---------- | ---------------- |

# 3) Deploy contract
Deployed `ETHPool` contract on goerli testnet and verified.
Address: [0x9386d6aac111db0229b1106f726acab1dfad7c7d](https://goerli.etherscan.io/address/0x9386d6aac111db0229b1106f726acab1dfad7c7d)

# 4) Interact with the contract
ETH Balance fetching script added in 2 ways using `provider.getBalance()` and `ethPool.getETHBalanceOfPool()`.