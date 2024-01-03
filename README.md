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

```solidity
struct bOracle{
        uint256 lastPrice;
        uint256 lastPriceUpdateTime; 
        uint256 maxDelay;
        address priceFeedAddress;
        bytes32 pythAddress1;
        bytes32 pythAddress2;
        bOrType oracleType;
        uint256 imA;
        uint256 imB;
        uint256 dfA; // Default Fee party A
        uint256 dfB; // Default Fee party B
        uint256 expiryA; // time where position can be closed at last oracle price
        uint256 expiryB;
        uint256 timeLockA; 
        uint256 timeLockB;
        cType cType;
        address kycAddress; 
        bool isPaused;
        uint256 deployTime;
        }
```

<table data-header-hidden><thead><tr><th></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td><pre><code>lastPrice
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>lastPriceUpdateTime
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>maxDelay
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>priceFeedAddress
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>pythAddress1
</code></pre></td><td></td><td></td></tr><tr><td><pre><code><strong>pythAddress2
</strong></code></pre></td><td></td><td></td></tr><tr><td><pre><code>oracleType
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>imA
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>imB
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>dfA
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>dfB
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>expiryA
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>expiryB
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>timeLockA
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>timeLockB
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>cType
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>kycAddress
</code></pre></td><td></td><td></td></tr><tr><td><pre><code>isPaused
</code></pre></td><td>Only Updatable by User KYC Admi</td><td></td></tr><tr><td><pre><code>deployTime
</code></pre></td><td></td><td></td></tr></tbody></table>
