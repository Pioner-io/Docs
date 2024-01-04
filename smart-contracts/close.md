---
description: PionerV1Close.sol
---

# 📪 Close



### `OpenCloseQuote`

Open a close quote, allowing a user asking for close limit, stop limit or send a notification of close market.

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

### There is multiple 3 ways of closing a positions :

### 1/ Close limit

e



### 2/ Close market

A normal market close is dangerous for the hedger, because&#x20;

Close market happens in 2 times, first user call openCloseQuote

```solidity
function closeMarket(uint256 bCloseQuoteId, uint256 index) public
```

### 3/ Stop limit

e



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

