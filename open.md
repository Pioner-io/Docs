---
description: PionerV1Open.sol
---

# 📬 Open

### Open an onchain quote&#x20;

```solidity
function openQuote( 
        bool isLong,
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



### Accept Quote :

r

```solidity
function acceptQuote(uint256 bContractId, uint256 _acceptPrice, address backendAffiliate) public
```

### Cancel Quote :

Return lock collateral to CA.

```solidity
function cancelOpenQuote( uint256 bContractId) public
```
