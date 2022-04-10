# Objective

This case study was aimed to build a Logistic Regression model for a company X Education to
predict which of the customers are likely to convert (i.e.: take up their online courses) and which
are not. The business requirement was to assign a lead score to each of the leads such that the
customers with higher lead score have a higher conversion chance and the customers with lower
lead score have a lower conversion chance.

# Process

Below steps were performed to arrive at the final model:

- Inspected the data and performed missing value analysis and imputations, wherever
needed.
- Outlier analysis was performed and no noticeable outliers were found.
- Identified the categorical variables and converted them to dummy variables using One
Hot Encoding methodology, in data preparation step. Since, the Specialization column
had ‘Select ‘value, it was dropped manually. Rest all categorical variables were dropped
using ‘dropfirst’ option.
- The Train-Test was split in 70-30 ratio and performed Min-Max Scaling on the numerical
variables.
- In the model building step, the RFE approach was used to select 15 columns and based
on the p-values and VIF manual feature elimination was performed to arrive at the final
model where all p-values were less than 0.05 and VIF<2.
- The business aspects were also taken into consideration while selecting the variables for
the model. The top 5 features after model building were:

-> TotalVisits
-> Total Time Spent on Website
-> Lead Origin_Lead Add Form
-> Lead Source_Olark Chat
-> Lead Source_Welingak Website
    
- Model Evaluation was performed to check for its accuracy, sensitivity and specificity.
ROC curve was plotted by taking the cut-off as 0.5 and the area under the curve was
equal to 0.86.
- In-order to find the optimal threshold the values of accuracy, sensitivity and specificity
were plotted together and the threshold was found to be at 0.42. At this value the
Accuracy, Sensitivity and Specificity were found to be around 79%.
- Finally, after performing predictions against the test data, the Accuracy, Sensitivity and
Specificity were found to be around 78%.
- As per the Conversion probability obtained, the lead score was calculated for each lead
and assigned it accordingly.

# Insights and Recommendations to the business

- The highest contributing columns to the Conversion probability were Total visits
followed by Total time spent on the Website and Lead_Origin_Add form. The sales
team should focus on these columns going forward to achieve a higher conversion rate.

- We need to target professionals who spend most of their time on the website by making
dedicated phone calls to them and if they seem interested could also offer some joining
discounts.

- To make the lead conversion more aggressive, the team can consider a cut-off giving
high sensitivity or Recall value. The team may consider a probability threshold of 0.4 to
achieve their target of 80% conversion rate.

- The sales team need not make unnecessary calls to leads those are not going to be
converted, in order to reduce Type 1 error. In this case the team may consider a cut-off
of 0.7 or 0.8 in order to achieve a low False Positive Rate (FPR) or high Specificity
