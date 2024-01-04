---
description: PionerV1Utils.sol
---

# 📜 Contract Structure

### Billateral contracts :

Each position state is represented as a Billateral Contract.

Functions update the state of the bConctract struct.

### bContract struct :&#x20;

<table><thead><tr><th></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td>pA</td><td>Party A - Long Party</td><td></td></tr><tr><td>pB</td><td>Party B - Short Party</td><td></td></tr><tr><td>oracleId</td><td>Id of bOracle set of rules</td><td></td></tr><tr><td>initiator</td><td>Used in the contract to define whom sent the quote.</td><td></td></tr><tr><td>price</td><td>Open price of the contract</td><td></td></tr><tr><td>qty</td><td>Number of contracts</td><td></td></tr><tr><td>interestRate</td><td>Yearly APR on Notional</td><td></td></tr><tr><td>isAPayingAPR</td><td>bool - Charging pA or pB paying interestRate</td><td></td></tr><tr><td>openTime</td><td>Time at last price update</td><td></td></tr><tr><td>cState</td><td>enum - Quote, Open, Closed, Liquidated</td><td></td></tr><tr><td>frontEnd</td><td>Share of Fees goes to the front end hosting the transaction.</td><td></td></tr><tr><td>affiliate</td><td>Frontend can keep that share to itself or distribute it with their own affiliate system</td><td></td></tr><tr><td>hedger</td><td>Hedging Bot Affiliate Address allowing a hedging bot provider to earn.</td><td></td></tr><tr><td>cancelTime</td><td>In case of cancel or default, give a few seconds for a hedger tx to pass. Hedger must be profitable before all.</td><td></td></tr></tbody></table>

### bOracle struct :

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
