---
description: PionerV1Compliance.sol
---

# 🧐 Compliance

KYC doesn't necessarily mean show me your passport. PionerV1 contains a set of KYC types with different rules.\
This compliance factory is made to adapt to any use case from fund management, OFAC compliance or trustless stablecoins.

<table><thead><tr><th></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td>Pirate</td><td>User is it's own KYC Manager</td><td></td></tr><tr><td>OneWayOneSide</td><td>Anyone can join KYC system ( For standardization usage )</td><td></td></tr><tr><td>TwoWayOneSide</td><td>KYC system with approval</td><td></td></tr><tr><td>OneWayTwoSide</td><td>Both Side Must be in the same KYCed system</td><td></td></tr><tr><td>TwoWayTwoSide</td><td>Account Must be approved by KYC Manager and Both party must be KYCed in the same system.</td><td></td></tr><tr><td>Mint</td><td>Stablecoin Account, subtype of OneWayOneSide</td><td></td></tr><tr><td>FundOneWay</td><td>Suscribe to a Fund Manager without approval OneSide by default, FundManager is responsible. </td><td></td></tr><tr><td>FundTwoWay</td><td>Suscribe to a Fund Manager with approval</td><td></td></tr><tr><td>FundManager</td><td>Manage Right of a Fund</td><td></td></tr><tr><td>Trusted</td><td>For Super Collateral Agreement ( Coming soon )</td><td></td></tr></tbody></table>



Set KYC for first deposit ( Mandatory )

```solidity
function deposit(uint256 _amount, utils.kycType _kyc, address _kycAddress ) public 
```



Function callable by kyc manager to approve a KYC appliance in case of TwoWay KYC type.

```solidity
function validateKyc(address target)
```

A kyc manager can revoke kyc :

```solidity
function revokeKyc(address target) public
```

Only the fundmanager can deploy bOracles for the kyc system.

Pause a bOracle

```solidity
function manageBOracle(uint256 bOracleId, bool isPaused) public
```

Pause all open and deposits :

```solidity
function pauseKyc(bool newState) public
```



