---
description: PionerV1Open.sol
---

# 📬 Open

### Open an onchain quote :&#x20;

Open quote with the following parameters, the quote will lock collateral requirements inputed in bOracleId associated struct and can be accepted by a counterparty.

For more details about parameters see [Contract Structure](contract-structure.md).

```solidity
function openQuote( 
        bool isLong, // Is initiator Long or Short
        uint256 bOracleId,
        uint256 price,
        uint256 qty,
        uint256 interestRate, 
        bool isAPayingAPR, 
        address frontEnd, 
        address affiliate
    ) public
```



<table data-header-hidden><thead><tr><th></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td>isLong</td><td>true : Long, false : Short</td><td></td></tr><tr><td>bOracleId</td><td>mapping Id of bOracle struct</td><td></td></tr><tr><td>price</td><td>open price</td><td></td></tr><tr><td>qty</td><td>number of contracts</td><td></td></tr><tr><td>interestRate</td><td>yearly interest rate</td><td></td></tr><tr><td>isAPayingAPR</td><td>true: Long side pays IR, false: Sort side pays IR</td><td></td></tr><tr><td>frontend</td><td>frontend affiliate address for fee share</td><td></td></tr><tr><td>affiliate</td><td>frontend affiliate, affiliate address for fee share</td><td></td></tr></tbody></table>

### Deploy bOracle and bContract at once :

To facilitate cases where contracts are not standardized, for example in pair trading, the quote more open also deploys a bOracle struct with suited parameters.

```solidity
function wrapperOpenQuoteSwap(bool isLong,
        uint256 price,
        uint256 qty,
        uint256 interestRate, 
        bool isAPayingAPR, 
        address frontEnd, 
        address affiliate,
        address _priceFeedAddress,
        bytes32 _pythAddress1,
        bytes32 _pythAddress2,
        uint256 _maxDelay,
        uint256 _imA,
        uint256 _imB,
        uint256 _dfA,
        uint256 _dfB,
        uint256 _expiryA,
        uint256 _expiryB,
        uint256 _timeLockA
        ) public
```

To deploy only a bOracle without a contract use this function :

```solidity
function deployBOracle(
        address _priceFeedAddress,
        bytes32 _pythAddress1,
        bytes32 _pythAddress2,
        uint256 _maxDelay,
        utils.bOrType _oracleType,
        uint256 _imA,
        uint256 _imB,
        uint256 _dfA,
        uint256 _dfB,
        uint256 _expiryA,
        uint256 _expiryB,
        uint256 _timeLockA,
        uint256 _timeLockB,
        utils.cType _cType 
    ) public
```

### Accept Quote :

Accept an open quote, lock collateral requirement an change the state of the contract from Quote -> Open.

```solidity
function acceptQuote(
        uint256 bContractId, 
        uint256 _acceptPrice, 
        address backendAffiliate
    ) public
```

### Cancel Quote :

Return lock collateral to CA if contract is still in Quote state.

```solidity
function cancelOpenQuote( uint256 bContractId) public
```
