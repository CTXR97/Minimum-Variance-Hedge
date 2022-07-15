# Minimum-Variance-Hedge

The minimum variance hedge ratio, also known as the optimal hedge ratio, is a formula to evaluate the correlation between the variance in the value of an asset or liability and that of the hedging instrument that is meant to protect it (hedge their exposure with futures contracts).

The hedge ratio is to find out the optimal number of contracts in order to offset their exposure to the potential changes in the value of their underlying asset or liability.

**Hedging with Futures**

**Short hedge**: A short hedge is appropriate when the hedger already owns an asset and expects to sell it at some time in the future.

**Long hedge:** A long hedge is appropriate when a company knows it will have to purchase a certain asset in the future and wants to lock in a price now.

**Data Cleansing:** 

In order to ensure consistency in the datasets, this part of the code requires user to determine the range of data to be used for analysis based on the row number.
>>> for example: SPOT = SPOT.iloc[:98,:] <<< iloc[row, column] allows user to determine the rows and columns based on integer index/position so in this case, it is selection from the start till row 98 and all columns. 

![image](https://user-images.githubusercontent.com/107907500/179127079-010c2f8a-3715-4fd3-8768-bee3774a2d28.png)

After selecting the same range of data, there were still inconsistencies in the data for example, TTF is traded on 15 July 2022 but CO1 is not so 15 July 2022 will not appear in CO1 dataset. The issue with this is that it will lead to very inaccurate results e.g correlation of 0.003 when it was expected to be 0.3. So this part of the code does the cleansing to ensure only data from the same dates are selected. 

![image](https://user-images.githubusercontent.com/107907500/179126783-86a6782a-97ce-410c-bcaf-d8bc782c68a8.png)

**Basis Risk — Futures**

The basis of a hedge is a measure of the difference between the spot price of the hedged asset and the futures price for the contact. Overtime, the basis will fluctuate and be zero at the future’s expiration date, assuming that the assets are the same.

<img width="526" alt="Screenshot 2022-07-11 at 4 21 22 PM" src="https://user-images.githubusercontent.com/107907500/178220454-d9edc7c0-12ae-43a1-8d3e-83039de95eec.png">

**Basis = (Spot price of asset to be hedged)-(Futures price of contract used)**

In this case to calculate the Basis risk, I am using the following formula: 

![image](https://user-images.githubusercontent.com/107907500/178881304-6297149c-5690-4bbe-99bb-dcda1de9e067.png)

whereby S = Spot, h = Hedged ratio, F = Futures

**To calculate the hedged ratio:**

![image](https://user-images.githubusercontent.com/107907500/178882722-df72e6bb-8b1e-443d-8e75-482ec4c7f7b4.png)

**To calculate the units hedged:**

<img width="476" alt="Screenshot 2022-07-11 at 12 06 22 AM" src="https://user-images.githubusercontent.com/107907500/178152611-3f037d2e-33db-4eb9-b8a6-44b501097e55.png">

**Risk reduction**
To calculate the risk reduction based on optimal hedge ratio, I used the following formula:

![image](https://user-images.githubusercontent.com/107907500/179131588-f2d838b4-a5bb-4c4d-ab8d-9cb45c5869c6.png)

>>>Require to confirm if formula is correct

**Final Results**
The final table will be as such: 

![image](https://user-images.githubusercontent.com/107907500/179129540-7227f5b8-f4ba-4637-9a67-6af6274d3c35.png)

**Regression test**
A a single linear regression is performed as well to find the best fit line, to test for the significance of the data based on f-test and t-test. 

![image](https://user-images.githubusercontent.com/107907500/179129711-b31d074e-5357-418c-9ed4-af4a91b01a31.png)

**Limitations of the model**

1. I cannot find a method to label each table with the exact contract's name for example "AUG22 Contract". Manual labelling is also not possible. Will try to see if there are any work arounds for this. 
