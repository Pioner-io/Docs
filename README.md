# PionerV1 Overview

PionerV1 is unique in its approach compared to other onchain derivatives projects in its liquidity provision. Each liquidity provider is isolated and runs a bot in the same way nodes and validators are run for blockchains that we call `Hedging Bot`.

Moreover, Pioner is an infrastructure project and doesn't run liquidity or exchange itself. Each exchange run by third parties will be called `Frontend.`

When a user comes on the Frontend and passes a trade, instead of being automatically accepted or matched with another quote, the Hedging Bot swarm source available liquidity from other exchanges, and individually accept the trade if they can create the same trade somewhere else.

For example, the User opens 5 TSLA Long, Hedging Bot accepts 5 TSLA Short.\
Hedging Bot opens 5 TSLA Long on MT5, allowing to not lose nor win on price change, but only benefit from fees and funding paid by the user.



The whole infrastructure is divided into 4 parts :&#x20;

* [Onchain smart contracts](smart-contracts/)
* [Oracles](smart-contracts/oracle.md)
* [API](api/)
* [Frontend](front-ends.md)
* [Hedging Bot](hedging-bots.md)



