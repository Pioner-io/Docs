---
description: PionerV1Default.sol
---

# 🔞 Settlements and Defaults

Settlement is the angular part of any asset cross margin features, it allows to dynamically isolate each trade but keeps a safe cross margin between each contract while ensuring margin in case of counterparty default to hedgers, allowing safe close of hedges.

* To reduce gas fees, IM requirements can be increased but it will decrease max leverage and decrease capital efficiency.
* For safe hedges, DF requirements can be increased to get enough liquidity to close a trade, but this will decrease capital efficiency and inflict a greater loss in case of default for the defaulting party. \


In the case where uPnL > IM \* Notional, the margin is not insured anymore, and the counterparty or anyone can call settleAndLiquidate.&#x20;

When calling IM, uPnL is settled for the CA of both parties, and openPrice is reset to the last oracle price.

A liquidation ( or default ) event occurs when the CA doesn't have enough collateral to replenish the IM.

Oracle price must be updated closely before calling settlements and default.

### `settleAndLiquidate`

Settlements and liquidations are treated in a single function to be called by ID of the underlying bContract.

```
function settleAndLiquidate(uint256 _bContractId)
```



### Third parties :

To incentivize a third party to call settleAndLiquidate by paying his gas fees, the following function can be called and will apply to all positions with the `msg.sender` address in pA or pB.

```solidity
function updateSponsorReward(uint256 newAmount) public
```



### Future updates :

* Settlement gas fees are negligible compared to derivative notional on L2, future updates come zk-settlement.
* Reputation system tracking extra DF returned, allowing honest hedgers to close more and more trades.

