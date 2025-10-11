# Marketing Campaign A/B Testing Analysis in Excel

## 1. 🧾 **Introduction**
This project focuses on analyzing the performance of two distinct marketing campaigns, a Control Campaign and a Test Campaign, both conducted during the period from **August 1** to **August 30**.

The goal of this analysis is to evaluate the effectiveness of each campaign based on multiple performance metrics such as **spending, impressions, website clicks, searches, content views, add-to-cart actions, and purchases**.

A/B Testing was used as the primary framework for comparison. This technique allows marketers and analysts to assess whether the observed differences between two campaign strategies are **statistically significant** or simply the result of random variation.

By combining **descriptive analysis** with **statistical testing**, this project aims to identify which campaign achieved better results and provide insights that can guide future marketing decisions.

## 2. 🎯 **Objective**
The main objective of this project is to **compare the performance** of the two marketing campaigns, Control and Test, to determine which one delivered better results during the campaign period.

Specifically, the analysis seeks to:

* Evaluate key performance metrics such as **Amount Spent, Impressions, Reach, Website Clicks, Searches, Content Views, Add to Cart, and Purchases**.

* Identify whether the observed differences between the two campaigns are **statistically significant** using hypothesis testing (T-test).

* Provide **data-driven insights** that can support marketing strategy optimization and improve future campaign performance.

Through this analysis, the project demonstrates how A/B testing can be used to guide **evidence-based decision-making** in digital marketing.

## 3. 📊 **Dataset Description**
* **Data Source**: The dataset was synthetically generated to simulate real-world digital marketing performance data for two e-commerce campaigns.

* **Time Period**: From **August 1st** to **August 30th**, covering **30 days** of campaign performance.

* **Columns Description**:
    * `Campaign Name`: Identifier of the marketing campaign (Test Campaign
     or Control Campaign).

    * `Date`: The specific day of observation.

    * `Spend (USD)`: Total daily advertising spend in USD.

    * `# of Impressions`: Number of times the ad was displayed to users.

    * `Reach`: Number of unique users who saw the ad.

    * `# of Website Clicks`: Number of times users clicked the ad and visited the website.

    * `# of Searches`: Number of searches made by users after clicking the ad.

    * `# of View Content`: Number of times users viewed product details or content.

    * `# of Add to Cart`: Number of users who added products to their cart.

    * `# of Purchase`: Number of completed purchases resulting from the campaign.

* **Dataset Size**:
    <br>**60** records in total (**30 days** for each campaign).
* **Notes**:
    * Some missing values and outliers were intentionally added to simulate real-world data imperfections.

    * Data cleaning and preparation were performed using Power Query to ensure data quality before analysis.

## 4. 🧹**Data Cleaning**
Before conducting any statistical analysis, the dataset was carefully cleaned to ensure accuracy and consistency.

* **Outlier Treatment**:
<br>Outliers were identified using **Z-scores** and visually confirmed with **box plots**.
Any value with a Z-score outside the range of **-3 to +3** was considered a potential outlier.
In the control dataset, one outlier was detected in the **# of Searches** column and replaced with the **median** value.
<br>After correction, all variables were found to be within the acceptable range, indicating no remaining outliers.

* **Handling Missing Values**:
<br>Missing values were replaced with the **mean** of each column after verifying data consistency.
This approach helped maintain the overall statistical balance without introducing bias.

* **Data Type Verification**:
<br>Each column’s data type was reviewed to ensure compatibility with further analysis.<br>
    
    * **Numeric columns** were properly formatted for statistical tests.

    * **Date columns** were converted to the correct date format.

    * **Categorical fields** such as Campaign Name were standardized.

## 5. 🔍 **Exploratory Data Analysis (EDA)**
The goal of this step was to gain a clear understanding of both marketing campaigns (Control and Test groups) before conducting any hypothesis testing.

### **5.1 Descriptive Statistics**
Descriptive statistics were generated for all numerical variables, including:
**Spend (USD), # of Impressions, Reach, # of Website Clicks, # of Searches, # of View Content, # of Add to Cart, and # of Purchase**.

These tables summarize the **mean, median, standard deviation, variance, minimum, and maximum** values for each campaign.

They provide a quick overview of how the performance metrics differ between the two groups.
    
#### **Test Campaign Descriptive Statistics**: 

| Value / Feature | Spend [USD]	| # of Impressions | Reach | # of Website Clicks | # of Searches | # of View Content | # of Add to Cart | # of Purchase |
| --------------- | ----------- | ---------------- | ----- | ------------------- | ------------- | ----------------- | ---------------- | ------------- | 
| Minimum         | 1,968        | 22,521          | 10,598 | 3,038              | 1,854         | 858               | 278              | 238           |
| Maximum         | 3,112        | 133,771         | 109,834 | 8,264             | 2,978         | 2,801             | 1,391            | 890           |
| Average         | 2,563        | 74,585          | 53,492 | 6,032              | 2,419         | 1,858             | 882              | 521           |
| Median          | 2,584        | 68,854          | 44,220 | 6,243              | 2,396         | 1,881             | 974              | 500           |
| Standard Deviation | 349      | 32,121           | 28,796 | 1,709              | 389           | 598               | 348              | 211           |
| Variance        | 121,583      | 1,031,782,887   | 829,196,701 | 2,919,202     | 151,121       | 357,191           | 120,815          | 44,541        |

#### **Control Campaign Descriptive Statistics**: 

| Value / Feature | Spend [USD]	| # of Impressions | Reach | # of Website Clicks | # of Searches | # of View Content | # of Add to Cart | # of Purchase |
| --------------- | ----------- | ---------------- | ----- | ------------------- | ------------- | ----------------- | ---------------- | ------------- | 
| Minimum         | 1,757        | 71,274          | 42,859 | 2,277              | 1,001         | 848               | 442              | 222           |
| Maximum         | 3,083        | 145,248         | 127,852 | 8,137             | 3,549         | 4,219             | 1,913            | 800           |
| Average         | 2,288        | 109,560         | 88,845 | 5,321              | 2,135         | 1,944             | 1,300              | 523           |
| Median          | 2,300        | 112,368         | 91,418 | 5,272              | 2,340         | 1,980             | 1,320              | 506           |
| Standard Deviation | 367      | 21,312           | 21,453 | 1,727              | 687           | 764               | 400              | 182           |
| Variance        | 134,935      | 454,188,364   | 460,215,231 | 2,981,851     | 472,022         | 583,729           | 160,297          | 33,055        |

### **5.2 Box Plots**
Box plots were created for each numerical column to visualize the data distribution and confirm that outliers were successfully handled.

All plots were saved in **1080p** resolution for clear presentation and future reference.

#### **Test Campaign Box Plots**:
The following plots show the data distribution for the test campaign metrics after cleaning:

<p align="center">
  <img src="./charts/test_data/1.distribution_of_spent_usd.jpg" width="400"/>
  <img src="./charts/test_data/2.distribution_of_count_of_impressions.jpg" width="400"/>
</p>

<p align="center">
  <img src="./charts/test_data/3.distribution_of_reach.jpg" width="400"/>
  <img src="./charts/test_data/4.distribution_of_count_of_website_clicks.jpg" width="400"/>
</p>

<p align="center">
  <img src="./charts/test_data/5.distribution_of_count_of_searches.jpg" width="400"/>
  <img src="./charts/test_data/6.distribution_of_count_of_view_content.jpg" width="400"/>
</p>

<p align="center">
  <img src="./charts/test_data/7.distribution_of_count_of_add_to_cart.jpg" width="400"/>
  <img src="./charts/test_data/8.distribution_of_count_of_purchase.jpg" width="400"/>
</p>

#### **Control Campaign Box Plots**:
Below are the box plots for the control campaign metrics after fixing outliers and missing values:

<p align="center">
  <img src="./charts/control_data/1.distribution_of_spent_usd.jpg" width="400"/>
  <img src="./charts/control_data/2.distribution_of_count_of_impressions.jpg" width="400"/>
</p>

<p align="center">
  <img src="./charts/control_data/3.distribution_of_reach.jpg" width="400"/>
  <img src="./charts/control_data/4.distribution_of_count_of_website_clicks.jpg" width="400"/>
</p>

<p align="center">
  <img src="./charts/control_data/5.distribution_of_count_of_searches.jpg" width="400"/>
  <img src="./charts/control_data/6.distribution_of_count_of_view_content.jpg" width="400"/>
</p>

<p align="center">
  <img src="./charts/control_data/7.distribution_of_count_of_add_to_cart.jpg" width="400"/>
  <img src="./charts/control_data/8.distribution_of_count_of_purchase.jpg" width="400"/>
</p>

### **5.3 Z-Score Summary**
To further validate the absence of outliers, Z-scores were calculated for each feature.

The results confirmed that all values fall within the range of **–3 to +3**, indicating no remaining outliers in either dataset.

#### **Test Campaign Z-score summary table**:

| Feature / Value | Minimum Z-score | Maximum Z-score | Outliers Detected |
| --------------- | --------------- | --------------- | ----------------- |
| **Spend (USD)** | -1.71               | 1.57            | **NO**        |
| **# of Impressions** | -1.62          | 1.84            | **NO**        |
| **Reach** | -1.49                     | 1.96            | **NO**        |
| **# of Website Clicks** | -1.75       | 1.31            | **NO**        |
| **# of Searches** | -1.45             | 1.44            | **NO**        |
| **# of View Content** | -1.67         | 1.58            | **NO**        |
| **# of Add to Cart** | -1.74          | 1.47            | **NO**        |
| **# of Purchase** | -1.34             | 1.75            | **NO**        |

#### **Control Campaign Z-score summary table**:

| Feature / Value | Minimum Z-score | Maximum Z-score | Outliers Detected |
| --------------- | --------------- | --------------- | ----------------- |
| **Spend (USD)** | -1.45               | 2.16            | **NO**        |
| **# of Impressions** | -1.80          | 1.67            | **NO**        |
| **Reach** | -2.14                     | 1.82            | **NO**        |
| **# of Website Clicks** | -1.76       | 1.63            | **NO**        |
| **# of Searches** | -1.65             | 2.06            | **NO**        |
| **# of View Content** | -1.43         | 2.98            | **NO**        |
| **# of Add to Cart** | -2.14          | 1.53            | **NO**        |
| **# of Purchase** | -1.65             | 1.52            | **NO**        |

## 6. 🧮 **A/B Testing**
### 🔹 **Objective**
The goal of this A/B test is to determine whether the performance metrics of the **Test Campaign** differ significantly from those of the **Control Campaign**, and to identify which campaign performed better across key KPIs.

### 🔹 **Methodology**
* **Test type**: Independent two-sample t-test (assuming equal or unequal variances based on F-test results).
* **Significance level (α)**: 0.05
* **Null hypothesis (H₀)**: There is no statistically significant difference between the means of the Control and Test groups.
* **Alternative hypothesis (H₁)**: There is a statistically significant difference between the means of the Control and Test groups.

The **F-test** was first used to check variance equality for each feature, and based on that, the appropriate **T-test** (equal or unequal variance) was applied.

### 🔹 **Variance Check (F-Test)**
| Feature | Test Variance | Control Variance | Variance Ratio (F-Test) | Type |
| ------- | ------------- | ---------------- | ----------------------- | ---- |
| **Spend [USD]** | 121,583 | 134,935  | 	1.11 |	**equal var** |
| **# of Impressions** | 1,031,782,887 | 454,188,364 |	2.27 | **unequal var** |
| **Reach** | 829,196,701 | 460,215,231 | 1.80 | **equal var** |
| **# of Website Clicks** | 2,919,202 | 2,981,851 | 1.02 | **equal var** |
| **# of Searches** | 151,121 | 472,022 | 3.12 | **unequal var** |
| **# of View Content** | 357,191	| 583,729	| 1.63 | **equal var** |
| **# of Add to Cart** | 120,815 | 160,297 | 1.33 | **equal var** |
| **# of Purchase** | 44,541 | 33,055 | 1.35 | **equal var** |

### 🔹 **T-Test Results**
| Feature             | Avg. Test Group | Avg. Control Group |  p-value | Significant (p < 0.05)? | Better Campaign |
| ------------------ | -------------- | ----------------- | ------- | --------------------- | ------------- |
| **Spend [USD]**         |           2,563 |              2,288 |   0.0043 |          **YES**          |       **TEST**      |
| **# of Impressions**    |          74,585 |            109,560 | 0.000008 |          **YES**          |     **CONTROL**     |
| **Reach**               |          53,492 |             88,845 | 0.000001 |          **YES**          |     **CONTROL**     |
| **# of Website Clicks** |           6,032 |              5,321 |    0.114 |         **NO**          |       **TEST**      |
| **# of Searches**       |           2,419 |              2,135 |   0.0549 |         **NO**          |       **TEST**      |
| **# of View Content**   |           1,858 |              1,944 |   0.6299 |         **NO**          |     **CONTROL**     |
| **# of Add to Cart**    |             882 |              1,300 | 0.000061 |          **YES**          |     **CONTROL**     |
| **# of Purchase**       |             521 |                523 |   0.9756 |         **NO**          |     **CONTROL**     |

### 🔹 **Interpretation**
* Metrics with **p-value < 0.05** show a **statistically significant** difference between the two campaigns.
* The **Control Campaign** significantly outperformed the Test in **Impressions, Reach, and Add to Cart**, suggesting stronger upper-funnel and mid-funnel performance.
* The **Test Campaign** achieved a significantly higher **Spend**, but this higher spending did not translate into better downstream results (e.g., conversions or purchases).
* For other metrics like **Website Clicks, Searches**, and **Purchases**, the differences were not **statistically significant**, meaning performance was similar between both campaigns.

### 🔹 **Conclusion**
The A/B testing results indicate that the **Control Campaign** delivered stronger engagement and conversion outcomes despite lower spending efficiency in the **Test Campaign**.

Future testing could focus on optimizing the **Test Campaign’s targeting or ad creative** to improve downstream metrics and achieve higher ROI.

## 7. 📊 **Results & Insights**
### 🔹 **Overall Performance Summary**
* The **Control Campaign** achieved higher **Impressions**, **Reach**, and **Add to Cart** rates, indicating better audience engagement and stronger top- and mid-funnel performance.
* The **Test Campaign** recorded higher **spending**, yet this increase did not lead to significantly better conversions or purchases.
* Conversion-related metrics such as **Website Clicks**, **Searches**, and **Purchases** showed no **statistically significant** difference between the two campaigns.

### 🔹 **Statistical Significance**
* Significant differences were confirmed for **Impressions**, **Reach**, and **Add to Cart** (p < 0.05).
* Differences in **Spend**, although statistically significant, did not reflect improved conversion efficiency.
* Other metrics had **p-values above 0.05**, meaning both campaigns performed similarly on those fronts.

### 🔹 **Key Insights**
1. **Control Campaign dominance**: Despite lower spending, it reached more users and generated more cart additionsو suggesting more effective targeting or creative content.
2. **Test Campaign inefficiency**: The higher budget did not translate into proportionally higher engagement or sales.
3. **Optimization opportunity**: Future A/B tests should adjust **audience segmentation**, **creative messaging**, and **budget allocation** to improve cost efficiency.
4. **Focus on conversion funnel**: Since both campaigns had similar purchase outcomes, further analysis should focus on post-click user behavior and checkout experience.

## 8. 🧭 **Recommendations**
1. **Reallocate budget based on performance**:<br>
  Since the Control Campaign achieved better reach and engagement with lower spending, future campaigns should adopt a similar cost structure and ad delivery strategy.
2. **Review creative content and targeting**:<br>
  The Test Campaign’s higher cost with limited improvement suggests potential issues in targeting or ad design. Testing alternative creatives or refining audience segmentation could improve ROI.
3. **Prioritize conversion optimization**:<br>
  As both campaigns showed similar purchase results, efforts should focus on improving the conversion journey, e.g., landing page design, checkout flow, or personalized offers.
4. **Conduct follow-up experiments**:<br>
  Run focused A/B tests on individual factors (e.g., ad copy, visuals, bidding strategy) to isolate what drives better engagement and sales.
5. **Integrate behavioral metrics**:<br>
  Consider adding data such as session duration, bounce rate, or engagement per user in future tests to gain deeper insights into audience response.

## 🧠 Skills Demonstrated
* Data Cleaning (handling missing values & outliers).
* Exploratory Data Analysis (descriptive statistics & visualizations).
* Statistical Testing (two-sample T-test for A/B comparison).
* Data Validation and Interpretation.
* Excel Functions and Power Query for transformation and analysis.

## 🧰 Tools Used
* **Microsoft Excel**: primary tool for data analysis and statistical testing.
* **Power Query**: used for data cleaning and transformation.