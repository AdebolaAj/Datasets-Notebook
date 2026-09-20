# Sales-Dataset-Notebook

### Purpose
The purpose of this notebook is to analyze the sales report which simulates real world transactions across different products, regions and customers. The dataset was gotten from kaggle. We want to use this data to view trends in products which could further influence real sales of these products. Point to note from the kaggle description, the sales dataset being used is not based on actual business information.

### Key Insights
From the data visualization, we notice two distinct facts in the screenshots provided, during holiday times/ winter months we see an increase in sales with the highest points being in November (around the black friday sales). We also see that a lot of these sales were for clothing with food being the lowest.

Fortunately this was a well prepared dataset so there was no missing data or outliers in values. The mean and median for this dataset are nearly identical as the mean is $5,019.27 while the median $5,019.30 this would suggest that sales are relatively balanced along the central line of distribution

From the correlation matrix, which is shown by the plotted chart in the screenshot, there is a strong positive relationship between the unit cost and unit price of products. As the costs of products increase, their selling prices also increased. Asides from this, most of the other variables show correlations close to zero suggesting a weaker linear relationship.

### Challenges and decisions
The main challenge I'll say was getting more acquainted with Jupyter as its the first time I have used it. In terms of decisions, I decided to use simulated data for more creative freedom. For example, involving outlier handling, I used the IQR method to identify unusual high or low values which is fine to remove. However, in real sales environment, such transactions would have to be investigated first before removal as they could be legitimate. 
