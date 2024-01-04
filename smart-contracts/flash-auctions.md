---
description: PionerV1Default.sol
---

# ⚡ Flash Auctions

PionerV1 is the first system to include retails as bilateral counterparty, this brings high counterparty risk that brings stress on UX.

When a user comes on Binance Futures, GMX, or RobinHood, he doesn't want his trade to be closed at a random time. Flash Auctions solve this, when a hedger defaults, another hedger in the few following blocks can buyback trade in exchange for DF.

```solidity
function flashDefaultAuction(uint256 bContractId) public
```

While this doesn't cover 100% of the case, with high enough DF and widespread bots that are incentives to buyback hedgers default, this reduces by a lot. Future work introduce CCP infrastructure to reduce this issue to 0%.

