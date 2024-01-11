# 🌊 Flows

#### RFQ Flow :

1 : Front send RFQ to API

2: Hedging Bot fetch all last API RFQs

3 : Hedging Bot answers a Quote to API&#x20;

4: Front Fetch Best Quotes from API.

5 : User from frontend push quote onchain with VAA if needed.

6 : Hedging Bot accepts Quote onchain.

7: Hedging Bot replicate position on Binance, MT5, RobinHood or other.

<figure><img src=".gitbook/assets/Closed_Alpha (28).jpg" alt=""><figcaption></figcaption></figure>



#### Liquidation Flow :&#x20;

1: Hedging bot identify position to settle because lack of IM.

2: Call settleAndLiquidate, if position is lacking of funds, will automatically liquidate the positon.\


<figure><img src=".gitbook/assets/Closed_Alpha (31) (1).jpg" alt=""><figcaption></figcaption></figure>

#### Close RFQ  :&#x20;

Same Flow as Open RFQ but with position ID.

<figure><img src=".gitbook/assets/Closed_Alpha (29).jpg" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/Closed_Alpha (30).jpg" alt=""><figcaption></figcaption></figure>

\




