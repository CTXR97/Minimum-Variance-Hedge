# Minimum-Variance-Hedge

**Hedging with Futures**

Although options are more commonly used for hedging than futures are, futures are still useful for hedging depending on the situation.
Short hedge: A short hedge is appropriate when the hedger already owns an asset and expects to sell it at some time in the future.
Long hedge: A long hedge is appropriate when a company knows it will have to purchase a certain asset in the future and wants to lock in a price now.

**Basis Risk — Futures**

The basis of a hedge is a measures of the difference between the spot price of the hedged asset and the futures price for the contact. Overtime, the basis will fluctuate and be zero at the future’s expiration date, assuming that the assets are the same.

<img width="526" alt="Screenshot 2022-07-11 at 4 21 22 PM" src="https://user-images.githubusercontent.com/107907500/178220454-d9edc7c0-12ae-43a1-8d3e-83039de95eec.png">

**Basis = (Spot price of asset to be hedged)-(Futures price of contract used)**

In this case to calculate the Basis risk, I am using the following formula: 

![image](https://user-images.githubusercontent.com/107907500/178881304-6297149c-5690-4bbe-99bb-dcda1de9e067.png)

whereby S = Spot, h = Hedged ratio, F = Futures

**To calculate the hedged ratio:**

![image](https://user-images.githubusercontent.com/107907500/178882722-df72e6bb-8b1e-443d-8e75-482ec4c7f7b4.png)

**To calculate the units hedged:**

<img width="476" alt="Screenshot 2022-07-11 at 12 06 22 AM" src="https://user-images.githubusercontent.com/107907500/178152611-3f037d2e-33db-4eb9-b8a6-44b501097e55.png">

Regression was also performed on a futures contract against a spot contract: to plot a best fit line: 

![image](https://user-images.githubusercontent.com/107907500/178883070-4a8085af-8fb9-4489-801c-eefae8a327fc.png)

Sample of the **regression results**: 

![image](https://user-images.githubusercontent.com/107907500/178883113-7f10e2e4-1064-44ab-a3df-174a94b23aca.png)

**Final Output**:

![image](https://user-images.githubusercontent.com/107907500/178883176-93d25e1c-060b-48ff-9852-2e18c7b2f6c8.png)

Note: In my backtest, I used TTF forward contracts and Brent as the spot rate. The results showed to be statistically insignificant and the "goodness of fit" i.e how does the model fits the data, based on the R^2 value is poor. This means that the model explains little to none of the variability of the response data around its mean. We can conclude that in this model, we cannot determine futures prices based on the spot price alone. 

