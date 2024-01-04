---
description: PionerV1.sol
---

# 🕵 Debt

PionerV1 includes a debt system where an account can be negative. This debt system is used for example where a position defaults, but a position is not yet settled, so extra losses are paid to the non-defaulting counterparty with the later gains. Similar mechanisms are in place in StableCoin Factory.

\
A debt can be paid with payOwed, but will be done automatically for each positive earning on CA through deposit or PnL gains, debts will be paid first.\


```solidity
function payOwed(uint256 amount, address target) public
```

Once a debt is paid, any party that has a debt with the defaulter can claim to earn up to paid debt. The function claimOwed allows to force someone to claim his earnings, for example, to force a defaulting counterparty to claim his earnings from another default.

```solidity
function claimOwed(address target, address receiver) public
```





