# Test significance of vehicle attributes on Claim Frequency and Claim Severety
This project analyzes the significance of various vehicle attributes on insurance claims.
The analysis aims to provide insights that can be useful for insurance companies in risk assessment and pricing.

The analysis was done using statistical methods and Machine learning methods.
## Table of Contents
- [Introduction](#introduction)
- [Data](#data)
- [Methodology](#methodology)
- [Results](#results)
- [Conclusion](#conclusion)
- [Installation](#installation)
- [Usage](#usage)
## Introduction
This project addresses a key inquiry from an insurance firm seeking to determine whether factors beyond the sum insured—such as vehicle age, make, body type, cubic capacity, and model—significantly influence claim severity and frequency. By leveraging historical claims data, this analysis models the claim experiences. The insights gained from this study would empower the actuarial team to assess the feasibility of incorporating additional variables into their insurance pricing strategies, ultimately enhancing risk assessment and pricing accuracy.
## Data
The analysis utilized a dataset comprising 45,445 insurance claims recorded over a specified period. The dataset included various characteristic variables that provide insights into the policyholder and insured vehicles:

Policyholder Characteristics:

Age
Education
Job
Marital Status
Seniority of Driver’s License
Insurance Policy Details:

Coverage Type
Payment Methods
Insured Vehicle Attributes:

Year of Manufacture (YOM)
Vehicle Make
Model
Color
Body Type
This rich dataset allowed for a comprehensive analysis of how these diverse factors may impact both claim severity and frequency.
Data preprocessing steps included: Data validation, data cleaning and feature engineering.


## Methodology
The methodology employed in this analysis comprised several key steps to explore the relationship between vehicle attributes and insurance claims:

Exploratory Data Analysis (EDA):

Initially, EDA was conducted to gain insights into the dataset, examining the distribution of key variables and identifying potential patterns and outliers.
Time series analysis was performed to assess trends over the period covered by the dataset, helping to understand how claim frequency and severity evolved over time.
A correlation matrix analysis was generated to evaluate the relationships between the various attributes and the target variables. The results indicated a lack of linear relationships between the independent variables and the target variable, suggesting the need for more advanced modeling techniques.
Modeling Phase:

Given the findings from the correlation analysis, The analysis proceeded to the modeling phase. For modeling claim severity, a Generalized Linear Model (GLM) with a Gamma distribution was employed. This approach allowed for a more accurate representation of the continuous nature of claim severity data.
For analyzing claim frequency in relation to vehicle attributes, a Poisson regression model was utilized. This model is particularly suited for count data, effectively capturing the relationship between the independent variables and the frequency of claims.
Additionally, an XGBoost model was implemented to further enhance the predictive capabilities for both claim severity and frequency. XGBoost is a powerful gradient boosting framework that optimizes predictive performance by handling complex interactions between features.
## Results
Results
The analysis yielded several significant findings regarding the influence of vehicle attributes on claim severity and frequency:

Intercept: The constant term of the GLM model indicates a baseline log of Gross Paid with a significant positive coefficient of 9.5628 (p < 0.001), suggesting a robust baseline relationship.

Vehicle Age: All age categories exhibited significant positive coefficients, with "New" vehicles having the highest impact (2.0244). This indicated that newer vehicles were associated with increased claims, likely due to higher repair costs associated with advanced technologies.

Cubic Capacity: Higher cubic capacities showed significant positive coefficients (0.5480 for "High" and 0.5354 for "Very High"), suggesting that vehicles with larger engines are linked to greater claim severity, as they tend to incur higher repair costs.

Carry Capacity: All categories of carry capacity (Small, Medium, Large, Very Large) correlated positively with Gross Paid, with "Small" vehicles showing the highest coefficient (1.0242). 

Body Type: Only Utility Vehicles displayed a significant positive impact (0.2319) compared to Passenger Cars, indicating that utility vehicles were more prone to higher claims.

Vehicle Make: Japanese vehicles showed a significant negative effect on expected Gross Paid (-0.4260), while Chinese vehicles exhibited an even greater negative impact (-0.9746), suggesting lower claim costs for these makes.

Color: Color categories generally did not show significant effects.


## Conclusion
Insights and Implications
The analysis highlights that both cubic capacity and carry capacity significantly influence gross payments, indicating that vehicles designed for utility are more likely to incur higher claims.
Newer vehicles significantly increase gross payments, aligning with higher repair costs.
Smaller engine capacities are linked to lower claim amounts, while higher cubic capacities correlate with increased potential for costly claims.
The relationship between carry capacity and gross payments indicated that larger vehicles may have lower risk profiles, resulting in fewer high-value claims.
Finally, luxury vehicles tend to contribute positively to gross payments, likely due to higher repair costs associated with their complex technologies.

## Installation
To run this project locally, clone the repository and install the necessary libraries.

```bash
git clone https://github.com/yourusername/vehicle-claim-analysis.git
cd vehicle-claim-analysis
pip install -r requirements.txt

 
