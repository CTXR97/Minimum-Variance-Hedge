# Minimum-Variance-Hedge

The minimum variance hedge ratio, also known as the optimal hedge ratio, is a formula to evaluate the correlation between the variance in the value of an asset or liability and that of the hedging instrument that is meant to protect it (hedge their exposure with futures contracts).

The hedge ratio is to find out the optimal number of contracts in order to offset their exposure to the potential changes in the value of their underlying asset or liability.


**Data Cleansing:** 

Assuming the data is in a form of a matrix with the horizontal axis referring to the different futures contracts while vertical axis refers to the dates, we need to select the specific contract i.e the specific column and to do that, I used an indexing method.
>>> In this case, cols [0, 36] means I am selecting columns 0 (which is the date col) and col 36 (which is the 31 Dec 22 contract). 

After selecting the specific column and applying the data transformation to the date fields, to re arrange them in descending order, we need to specify the rows used for the analysis as well. Reason for doing so is to ensure consistency. If the number of rows in the dataset are the same, then there isn't a need to specify the rows already. However, there are situations whereby the data is inconsistent, so recommended to keep it. 
>>> iloc[:678, :] means I am selecting all rows till row 678 and all columns. 

![image](https://user-images.githubusercontent.com/107907500/179689326-6aabbc33-dc1e-4302-9f7c-0dba72eb5df7.png)

Another redundancy to ensure the datasets are consistent, a date filter is also applied - this helps to ensure that the dates used for analysis are the same. Because based on backtests, there were scenarios whereby the dates were inconsistent due to different trading dates. 

![image](https://user-images.githubusercontent.com/107907500/179690488-e8746937-c574-4c30-81fe-a443d351c057.png)

**User input**

The model also requires user to input the amount of exposure user is hedging against as well as the price of the futures contract

![image](https://user-images.githubusercontent.com/107907500/179187006-7d6e8926-2802-4a92-95ea-560d1becedd7.png)

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

**F-Test Hyptheses**:

Null hypothesis: The fit of the intercept-only model and my model are equal.i.e no independent variable x

Alternative hypothesis: The fit of the intercept-only model is significantly reduced compared to my model.

**T-Test Hyptheses**:

Null hypothesis: there is no relationship between the predictor variable and the response variable

Alternative hypothesis: there is a relationship between the predictor variable and the response variable

![image](https://user-images.githubusercontent.com/107907500/179158389-c5bea629-ffe2-46c7-8b8d-63fe9793e5dc.png)

**Limitations of the model**

1. I cannot find a method to label each table with the exact contract's name for example "AUG22 Contract", "SEP22 Contract". Manual labelling is also not possible because for this model, I am allowing it to run in loops to reduce the need for human intervention i.e to make amendments in the calculation engine.
