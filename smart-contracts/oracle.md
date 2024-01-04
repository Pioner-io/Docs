# 🧙♂ Oracle

Oracle is used to secure each trade price, on open both traders agree on a price, no oracle is needed, but to close a position, both parties need to agree, and if that is not the case, an oracle should be able to be used to not lock of the trade if 1 party doesn't answer.

Current Oracles is pyth.network but will evolve for better profitability for the hedger.

Before each Close or Settle\&Liquidate price must be updated.

### Pyth Oracle :

```solidity
function updatePricePyth( uint256 bOracleId, bytes[] memory _updateData1, bytes[] memory _updateData2) public
```

<table data-header-hidden><thead><tr><th>Inputs</th><th></th><th data-hidden></th></tr></thead><tbody><tr><td><pre><code>bOracleId
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>_updateData1
</code></pre></td><td>VAA for pythAddres1</td><td></td></tr><tr><td><pre><code>_updateData2
</code></pre></td><td>VAA for pythAddres2</td><td></td></tr></tbody></table>



### Dummy :&#x20;

```solidity
updatePriceDummy(uint256 bOracleId, uint256 price, uint256 time)
```

<table data-header-hidden><thead><tr><th>Inputs</th><th></th><th data-hidden></th></tr></thead><tbody><tr><td><pre><code>bOracleId
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>price
</code></pre></td><td>Asset1 / Asset2 Price</td><td></td></tr><tr><td><pre><code>time
</code></pre></td><td>Update time</td><td></td></tr></tbody></table>

