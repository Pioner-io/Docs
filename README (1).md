---
description: PionerV1Utils.sol
---

# 📜 Contract Structure

### Billateral contracts :

Each position state is represented as a Billateral Contract.

Functions update the state of the bConctract struct.

```solidity
struct bContract { 
        address pA; // partyA Long
        address pB; // partyB Short
        uint256 oracleId; // bOracle struct mapping Id
        address initiator; // quote party
        uint256 price;
        uint256 qty;
        uint256 interestRate; 
        bool isAPayingAPR; // party who pays interest rates
        uint256 openTime;
        cState state;
        address frontEnd; // frontend affiliate
        address hedger; // trading bot affiliate
        address affiliate; // affiliate ( defined by a cookie on frontend )
        uint256 cancelTime;
    }
```

bOracle struct defines standardized contracts

<table data-header-hidden><thead><tr><th></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td><pre><code>lastPrice
</code></pre></td><td>Last Price Value</td><td></td></tr><tr><td><pre><code>lastPriceUpdateTime
</code></pre></td><td>Last Price Update Time</td><td></td></tr><tr><td><pre><code>maxDelay
</code></pre></td><td>Maximum Delay from last Price allowed</td><td></td></tr><tr><td><pre><code>priceFeedAddress
</code></pre></td><td>Pyth Contract Verifier Address</td><td></td></tr><tr><td><pre><code>pythAddress1 / pythAddress2
</code></pre></td><td>put pyth VAA here</td><td></td></tr><tr><td><pre><code>oracleType
</code></pre></td><td>Pyth or Dummy</td><td></td></tr><tr><td><pre><code>imA / imB
</code></pre></td><td>Initial Margin</td><td></td></tr><tr><td><pre><code>dfA / dfB
</code></pre></td><td>Default Fee of Party A, this Fee is frozen and liberated on close, or provided to non defaulting party in case of Default.</td><td></td></tr><tr><td><pre><code>expiryA / expiryB
</code></pre></td><td>Time from Close Market is allowed</td><td></td></tr><tr><td><pre><code>timeLockA / timeLockB
</code></pre></td><td>Time from expiration is allowed</td><td></td></tr><tr><td><pre><code>cType
</code></pre></td><td>Contract type, swap, options, mint</td><td></td></tr><tr><td><pre><code>kycAddress
</code></pre></td><td>Kyc Manager Address set on creation</td><td></td></tr><tr><td><pre><code>isPaused
</code></pre></td><td>Only Updatable by User KYC Admi</td><td></td></tr><tr><td><pre><code>deployTime
</code></pre></td><td></td><td></td></tr></tbody></table>
