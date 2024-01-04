---
description: PionerV1Compliance.sol
---

# ✅ Deposit and Withdraw

Deposit by calling this function

```solidity
function deposit(uint256 _amount) public 
```

Withdraw by calling this function, tokens withdrawn are frozen for 5 minutes and can be used by the contract in case of liquidation before their claimed period. This provide a time buffer for settlement and oracle disputes.

```solidity
function initiateWithdraw(uint256 _amount) public
```

After GRACE\_PERIOD = 5 minutes is passed you can call this function to claim token to the wallet.

```solidity
function withdraw(uint256 _amount) public
```

