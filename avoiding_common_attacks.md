# Attack Vector Avoidance
.
1) No use of `tx.origin` authentication (https://swcregistry.io/docs/SWC-115)
2) Improper access control is avoided by using `onlyOwner` (`LegalDoc.sol` line 18) as a restriction in the mint function (https://swcregistry.io/docs/SWC-105).
3) Locked pragma solidity compiler version at 0.7.4. No floating pragma will not permit the contract to be compiled with an older compiler that may allow bugs into the contract (https://swcregistry.io/docs/SWC-103).