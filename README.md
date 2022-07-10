# Minimum-Variance-Hedge

Given the presence of basis risk, the minimum-variance hedge is a means to hedge if the assets are different, as in a cross-hedge. When a trader enters a cross-hedge, they are using different assets to hedge.

Let’s first construct a cash flow for a hedge.
<img width="623" alt="Screenshot 2022-07-11 at 12 05 15 AM" src="https://user-images.githubusercontent.com/107907500/178152560-b970c693-2665-49aa-9dcb-454f847f7213.png">

<img width="625" alt="Screenshot 2022-07-11 at 12 05 33 AM" src="https://user-images.githubusercontent.com/107907500/178152576-80a71dd9-f864-436e-aa52-806b58ca2218.png">

We can use beta, the correlation coefficient, instead of the equation above if the obligation has is for a fixed notional hedge amount. Effectively,


<img width="254" alt="Screenshot 2022-07-11 at 12 06 03 AM" src="https://user-images.githubusercontent.com/107907500/178152600-1db8299f-d1a9-4c08-93dd-c29e864890f1.png">

Once we have found the optimal hedge ratio, we can find the number of futures contracts to purchase.

<img width="476" alt="Screenshot 2022-07-11 at 12 06 22 AM" src="https://user-images.githubusercontent.com/107907500/178152611-3f037d2e-33db-4eb9-b8a6-44b501097e55.png">

In Python Code (To-do):
1. Find the variance of Spot
2. Find the variance of Fut
3. Find the Correlation
4. Formulate the hedge ratio
5. Based on the hedge ratio, define a function to allow user to input notional amount and price of futures to get hedge units


<img width="585" alt="Screenshot 2022-07-11 at 12 16 02 AM" src="https://user-images.githubusercontent.com/107907500/178152940-3c996cc6-cc5a-4ef2-8e19-cba1f2913d72.png">

