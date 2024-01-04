---
description: PionerV1Close.sol
---

# 📪 Close

Closing a contract is where all attacks can happen on PionerV1, and crucial to be compatible by hedging bots profitability.

### `OpenCloseQuote`

Open a close quote, allowing a user to ask for close limit, stop limit, or send a notification of close market.

Allow in 1 click to close multiple bContract on the same asset but different bOracleId, for example in the case of a Close All button.

```solidity
function openCloseQuote(
        uint256[] memory bContractIds,
        uint256[] memory price, 
        uint256[] memory qty, 
        uint256[] memory limitOrStop, 
        uint256[] memory expiry
    ) ;
```

{% tabs %}
{% tab title="" %}
| Parameter    | Type       | Description                |
| ------------ | ---------- | -------------------------- |
| bContractIds | uint256\[] | Id of each open contracts  |
| price        | uint256\[] | Limit Price                |
| qty          | uint256\[] | Quantity                   |
| limitOrStop  | uint256\[] | 0 if limit a price if Stop |
| expiry       | uint256\[] | Time where order expire.   |
{% endtab %}
{% endtabs %}

### 5 ways of closing positions:

### 1/ Close limit :&#x20;

After a close quote is triggered, the counterparty of the close quote initiate can call this function. This function can be called with a specific amount in the case where the counterparty is hedging on another market and his closing order hasn't been fully filled.

bCloseQuoteId is the mapping ID of the close quote.

index is the index limit id inside the closeQuote.

```solidity
acceptCloseQuote( uint256 bCloseQuoteId, uint256 index, uint256 amount ) public
```



### 2/ Close market

Close market to close at market price, this close option can only be called if the underlying party expiration parameters date is past. Before that date, only bi-parties limit close.

The close market happens in 2 times because a normal market close would be dangerous for the hedger because it can be triggered in low liquidity ph

First user calls openCloseQuote, and then we let the time hedging bot react to place an order on the market, if the price for a sell is above the closeQuote price, then this means that the market has bounced on the hedger order.

```solidity
function closeMarket(uint256 bCloseQuoteId, uint256 index) public
```

### 3/ Stop limit

Same call as for the close limit but with a check to verify if the stop price is below or above the current Oracle price.

```solidity
acceptCloseQuote( uint256 bCloseQuoteId, uint256 index, uint256 amount ) public
```

### 4/ Position Expiration

e

```solidity
function expirateBContract( uint256 bContractId) public
```

In the case where Oracle is out for 7 days, allow to expire position at last price.

```solidity
function expirateBContractOracleTimeout( uint256 bContractId) public
```

### 5/ Default&#x20;

The case where one of the parties is margin called.

Forward to [Settlements and Defaults](settlements-and-defaults.md)



### Cancel CloseQuote :&#x20;

Set the closeQuote state to Closed.

```solidity
function cancelCloseQuote(uint256 bCloseQuoteId)
```

After a cancelCloseQuote, the counterparty has a few blocks to react in case his closing hedge order has been partially filled or filled.
