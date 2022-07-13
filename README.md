# Minimum-Variance-Hedge

Hedging with Futures
Although options are more commonly used for hedging than futures are, futures are still useful for hedging depending on the situation.
Short hedge: A short hedge is appropriate when the hedger already owns an asset and expects to sell it at some time in the future.
Long hedge: A long hedge is appropriate when a company knows it will have to purchase a certain asset in the future and wants to lock in a price now.

Basis Risk — Futures

The price of the asset being hedged may be different than the asset that is underlying the futures contract.
The hedger may not known the exact date when an asset will be bought or sold.
The hedge may require the futures contract to be closed before its delivery month.

These problems give rise to Basis Risk.

The basis of a hedge is a measures of the difference between the spot price of the hedged asset and the futures price for the contact. Overtime, the basis will fluctuate and be zero at the future’s expiration date, assuming that the assets are the same.

Basis = (Spot price of asset to be hedged)-(Futures price of contract used)

<img width="517" alt="Screenshot 2022-07-11 at 4 21 12 PM" src="https://user-images.githubusercontent.com/107907500/178220425-f9f594f5-2555-40cf-b8b7-3956d5b5942e.png">

<img width="526" alt="Screenshot 2022-07-11 at 4 21 22 PM" src="https://user-images.githubusercontent.com/107907500/178220454-d9edc7c0-12ae-43a1-8d3e-83039de95eec.png">

If the assets are not the same, the formula for basis can be easily modified,

<img width="675" alt="Screenshot 2022-07-11 at 4 21 44 PM" src="https://user-images.githubusercontent.com/107907500/178220528-d7346ddf-a508-469a-afd7-b969a6152c90.png">

<img width="673" alt="Screenshot 2022-07-11 at 4 23 07 PM" src="https://user-images.githubusercontent.com/107907500/178220798-31bac059-f553-4b49-b7bb-a25a05685896.png">


Given the presence of basis risk, the minimum-variance hedge is a means to hedge if the assets are different, as in a cross-hedge. When a trader enters a cross-hedge, they are using different assets to hedge.

Let’s first construct a cash flow for a hedge.
<img width="623" alt="Screenshot 2022-07-11 at 12 05 15 AM" src="https://user-images.githubusercontent.com/107907500/178152560-b970c693-2665-49aa-9dcb-454f847f7213.png">

<img width="625" alt="Screenshot 2022-07-11 at 12 05 33 AM" src="https://user-images.githubusercontent.com/107907500/178152576-80a71dd9-f864-436e-aa52-806b58ca2218.png">

We can use beta, the correlation coefficient, instead of the equation above if the obligation has is for a fixed notional hedge amount. Effectively,


<img width="254" alt="Screenshot 2022-07-11 at 12 06 03 AM" src="https://user-images.githubusercontent.com/107907500/178152600-1db8299f-d1a9-4c08-93dd-c29e864890f1.png">

<img width="613" alt="Screenshot 2022-07-11 at 12 17 10 AM" src="https://user-images.githubusercontent.com/107907500/178152995-9d46d02a-93e7-4829-b3a7-6bf48f0c3d59.png">

Once we have found the optimal hedge ratio, we can find the number of futures contracts to purchase.

<img width="476" alt="Screenshot 2022-07-11 at 12 06 22 AM" src="https://user-images.githubusercontent.com/107907500/178152611-3f037d2e-33db-4eb9-b8a6-44b501097e55.png">

