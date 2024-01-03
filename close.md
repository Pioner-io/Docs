---
description: PionerV1Close.sol
---

# 📪 Close

Open close quote takes multiple bContractId as input,&#x20;

To make a force close all button on the frontend

Allow in 1 click to close multiple bContract on the same asset but different bOracleId.&#x20;

<pre class="language-solidity"><code class="lang-solidity"><strong>function openCloseQuote(
</strong>        uint256[] memory bContractIds,
        uint256[] memory price, 
        uint256[] memory qty, 
        uint256[] memory limitOrStop, 
        uint256 expiration, 
        address initiator
    ) public

</code></pre>

There is multiple types way of closing a positions

### `OpenCloseQuote`

Emitted when liquidity has been removed from the inverse bonding curve.&#x20;

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
{% tab title="Parameters" %}
| Parameter    | Type    | Description                            |
| ------------ | ------- | -------------------------------------- |
| bContractIds | uint256 | Address of LP                          |
| price        | uint256 | Address that received removed reserves |
| qty          | uint256 | Amount of LP tokens burnt              |
| limitOrStop  | uint256 | Amount of reserve assets withdrawn     |
| expiry       | uint256 | ibAsset credit of LP prior to removal  |
{% endtab %}
{% endtabs %}



### `TokenStaked`

### Close limit



### Close market



### Stop limit



### Position Expiration

