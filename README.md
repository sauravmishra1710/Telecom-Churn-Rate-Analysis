# Telecom-Churn-Rate-Analysis
In the telecom industry, customers are able to choose from multiple service providers and actively switch from one operator to another. In this highly competitive market, the telecommunications industry experiences an average of **15-25% annual churn rate**. Given the fact that it costs 5-10 times more to acquire a new customer than to retain an existing one, customer retention has now become even more important than customer acquisition.

For many incumbent operators, retaining high profitable customers is the number one business goal.

To reduce customer churn, telecom companies need to predict which customers are at **high risk** of churn.

In this analysis, we will analyse customer-level data of a telecom firm, build predictive models to identify customers at high risk of churn and identify the main indicators of churn.

# Definitions of Churn

The churn rate, also known as the rate of attrition, is most commonly known as the percentage of service subscribers who discontinue their subscriptions within a given time period.

## Revenue-based churn: 
  Customers who have not utilised any revenue-generating facilities such as mobile internet, outgoing calls, SMS etc. over a given period of time. 
The main shortcoming of this definition is that there are customers who only receive calls/SMSes from their wage-earning counterparts, i.e. they don’t generate revenue but use the services. For example, many users in rural areas only receive calls from their wage-earning siblings in urban areas.

 ## Usage-based churn:
  Customers who have not done any usage, either incoming or outgoing - in terms of calls, internet etc. over a period of time.
A potential shortcoming of this definition is that when the customer has stopped using the services for a while, it may be too late to take any corrective actions to retain them. For e.g., if you define churn based on a ‘two-months zero usage’ period, predicting churn could be useless since by that time the customer would have already switched to another operator.

# Understanding the Business Objective and the Data

Our dataset contains customer-level information for a span of four consecutive months - June, July, August and September. The months are encoded as 6, 7, 8 and 9, respectively. 

The business objective is to predict the churn in the last (i.e. the ninth) month using the data for the first three months. 

**To do this task well, understanding the typical customer behaviour during churn will be helpful.**

# Understanding Customer Behaviour Over 3 Phases

Customers usually do not decide to switch to another competitor instantly, but rather over a period of time (this is especially applicable to high-value customers). In churn prediction, we assume that there are three phases of customer lifecycle-

The **‘GOOD’** phase: In this phase, the customer is happy with the service and behaves as usual.

The **‘ACTION’** phase: The customer experience starts to sore in this phase, for e.g. he/she gets a compelling offer from a  competitor, faces unjust charges, becomes unhappy with service quality etc. In this phase, the customer usually shows different behaviour than the ‘good’ months. Also, it is crucial to identify high-churn-risk customers in this phase, since some corrective actions can be taken at this point (such as matching the competitor’s offer/improving the service quality etc.)

The **‘CHURN’** phase: In this phase, the customer is said to have churned. You define churn based on this phase. Also, it is important to note that at the time of prediction (i.e. the action months), this data is not available to you for prediction. Thus, after tagging churn as 1/0 based on this phase, you discard all data corresponding to this phase.

 For this analysis, we will divide our data into three phases as - 
 - the first two months are the ‘good’ phase. 
 - the third month is the ‘action’ phase.
 - the fourth month is the ‘churn’ phase.
 
 We will build multiple models and finally recommend the best model that best predicts the churn behavior over the three phases.
