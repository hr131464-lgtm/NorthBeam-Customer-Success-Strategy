## The assumptions I take

The data set contains no business rules therefore, I have made an assumptions based on common practices of Customer Success.For this I need to take multiple factors. I am examing product usage(Seat utilization),customer satisfaction(CSAT), support log history, the value of the contract and the date of last renewal.
I will assume the more customer uses the product the less likely to churn. Because I will consider both seat utilization and monthly active user to be positive contributing variable in the overall health of a customer.
When it comes to customer satisfaction, I will assume that a higher score means the customer is more satisfied with our products services. Additionally, some customers did not have a score to report so for that customers I replaced the missing value with the median score so all customers.
I will assume that customers whose contract are ending within 10 days should be given higher  priority, since the customers will be renewing soon.

## Prioritization Logic/Score

To determine priority scores:
This is a rule based scoring system. Each customer received points based on different business metrics.
The score range for each characteristic can be found by analyzing the data and applying a basic understanding of business principles. Customers who received higher values will have higher scores.
The customer health score was calculated by summing the scores of all of the characteristics.
Customers were grouped into three categories based on their score:
. Healthy (score of 80 or higher) 
. Monitoring (score between 50 and 79) 
. At Risk (score less than 50)


To determine priority scores, I used 3 criteria:
1. 50% will be based upon how healthy customers are so if a customer has less healthy status, they will have a relative priority.
2. 30% will be based upon how large an annual contract value a customer has with us therefore, if a customer has a higher value contract, they will receive greater priority.
3. 20% will be based upon how soon a customer needs to renew, so if the customer has a renewal prepared for its due date, they'll be given the highest possible priority.

## Judgment Calls During Data Preparation
While cleaning the data, I made a few practical decisions.
The missing CSAT values were replaced with the median of the available values and a new column was created to indicate which values had originally been missing.
Records with active seats that were greater than their licensed seats were corrected.
The date columns were changed to a date/time format which allows me to find out how many days are left before the renewal date for each record.
I looked for correlations between features in the data and while some features appear to have a correlation to one another, I did not remove them from the data set because the project uses a rule-based scoring system as opposed to machine learning methods for determining the scores.


## Trade-offs and Future Improvements
One limitation is that the scoring depends on the rules and weights I selected. If more business data was available, the scoring could be made more accurate.
In the future, I would improve the model by using historical customer data, reviewing the scoring rules regularly.