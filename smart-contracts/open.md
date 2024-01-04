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

Accept an open quote, lock collateral requirement an change the state of the contract from Quote -> Open

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
