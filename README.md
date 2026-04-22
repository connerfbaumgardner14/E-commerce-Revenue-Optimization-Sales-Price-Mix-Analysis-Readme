# Project Abstract  
A sales price mix analysis was conducted for Royal Bounties Supply Co. to identify opportunities in the item price sales mix to increase overall revenue through purchases via their website. Items under $4 account for 90% of unit sales and 65% of revenue, while items over $4 contribute 35% of total revenue from only 10% of unit sales, indicating a potential for increased revenue by boosting sales in the higher-priced segment. Recommendations to address this include expanding the higher-priced product catalog, using "Best Seller" labels to drive unit sales, and implementing a "suggested items" feature to promote items over $4 to returning customers who typically buy lower-priced goods.

# Background  
Royal Bounties Supply Co.\* is a newly founded UK based online distributor that specializes in selling “unique all-occassion gifts” to wholesalers via their website. It is partially owned by a venture capital firm called G.R.Q. Enterprises that is primarily investing in the company. The firm is currently not as worried about profit but more concerned about quickly growing the company’s value through increased revenue. The ecommerce team is interested in increasing overall revenue through finding opportunities in the item price sales distribution / mix. They have asked me to analyze sales from the last 20 months and present various options for next steps to the President and Vice-President of Ecommerce. 

\- The SQL queries used to inspect and clean the data for this analysis can be found here \[link\].   
\- Targeted SQL queries regarding various business questions can be found here \[link\].   
\- The Tableau dashboard used to report and explore sales trends can be found here \[link\].

\* Royal Bounties Supply Co. and G.R.Q  are both fictional entities. The situation above is fictional and meant to help add context and direction to the analysis provided. The dataset used for this is donated data from an actual company between 01/12/2010 and 09/12/2011 for a UK-based company.

# Data Structure Overview  
The company's main database structure as seen below consists of one table. There were \_ rows in the data that was analyzed. 

| Variable Name | Role | Type | Description |
| ----- | ----- | ----- | ----- |
| InvoiceNo | ID | Categorical | a 6-digit integral number uniquely assigned to each transaction. If this code starts with letter 'c', it indicates a cancellation |
| StockCode | ID | Categorical | a 5-digit integral number uniquely assigned to each distinct product |
| Description | Feature | Categorical | product name |
| Quantity | Feature | Integer | the quantities of each product (item) per transaction |
| InvoiceDate | Feature | Date | the day and time when each transaction was generated |
| UnitPrice | Feature | Continuous | product price per unit |
| CustomerID | Feature | Categorical | a 5-digit integral number uniquely assigned to each customer |
| Country | Feature | Categorical | the name of the country where each customer resides |

# Executive Summary   
Items under $4 account for 90% of unit sales, but the higher revenue per item from goods over $4, which constitute 35% of total revenue from just 10% of unit sales, presents a significant opportunity to increase overall revenue. This current focus on lower-priced items is partially due to the current limited customer interest and a limited number of higher priced products, as only 24% of unique products are priced above the $4 mark.   

# General Insights   
90% of unit sales (Fig. 1\) and 65% of revenue (Fig. 2\) came from items under $4, indicating an opportunity to potentially increase revenue by focusing attention on increasing sales on items over $4. While items over $4 constituted only 10% of sales (Fig 1.), they made up 35% of revenue (Fig. 2), showcasing that a small increase of unit sales of items over $4 could impact revenue by a significant amount.  

One of the reasons for this high concentration of sales for low cost items is that over 20% of invoices did not contain items $4 or more, while only 4% of invoices did not contain items $4 or less (Fig. 3). Showcasing that, currently, customers seem to express less interest in our higher cost items compared to our lower cost items.   

However, we currently do not give our customers as many options that are above $4 as only 24% of the unique products offered are priced over $4 (Fig. 4). We may potentially be missing out in sales for customers looking for more expensive products (though more research on this is needed to confirm this).   

Despite low sales of more products above $4, products in the $4 to $14 range tend to yield an average revenue per item that is comparable to or greater than items under $4 (Fig. 5). Showcasing an opportunity where just increasing our sale of products above $4 by just a bit could amount to a significant revenue increase.  

# Recommendations  
Based on the insights and findings above, we would recommend the ecommerce team to consider the following:

### **Suggestion 1**  
Only 24% of items were above $4, therefore we could sell additional products above $4 based on additional research on customer demand / needs. Because of the higher prices of these items, we wouldn’t need to add a lot of new products in order to significantly increase revenue. 

### **Suggestion 2**  
Units priced above $4 only account To increase the unit sales of products priced above $4 (which currently account for only 10% of total unit sales), we recommend labeling certain items above $4 as "Best Seller" and incorporating strong customer testimonials. Customers are more likely to adopt behaviors when they perceive others, especially peers, doing so.  and labeling items as “Bestseller” has been shown to increase sales1. We could utilize customer surveys and market research to create a strategy and A/B testing to check and verify effectiveness.  . 

### **Suggestion 3**  
To address the fact that 20% of invoices exclude items over $4, we recommend implementing the research-backed “Foot-In-The-Door” technique. This sales tactic “...consists in proposing a little first request to a subject then to submit him/her a second more expensive request”2. To apply this strategy, we could program the "suggested items" section towards the bottom of an item description to promote products priced at $4 or more to returning customers who typically purchase lower-priced goods. Suggestions should feature a balance of items similar to past purchases and new, higher-priced items related to their current transaction.

### **Suggestion 4**  
When preparing the analysis, the goal was to check which item categories generated the most revenue to guide decisions. However, item categories are not currently logged in the data structure. Categorizing each item and applying those categories to the product list is recommended to better understand the sales mix. Once that's done, a follow-up analysis specifically on category sales mix is recommended.

# Caveats  
Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below: 

### **Assumption 1:**   
A total of 135,080 rows (approximately one-fifth of all transactions) contained blank values in the Customer ID column. These entries were retained to ensure the inclusion of all genuine transactions for analytic purposes. Given this significant absence of customer identifiers, the analysis was restricted to an item and transaction-centered perspective to avoid potentially misleading customer-specific findings.

### **Assumption 2**:   
 There were 9288 rows determined to be returns/cancellations and were included in the analysis to help not count items that were returned. They were subtracted from the grand total when items were summed together to ensure that the final sum accurately reflected net sales and items sold. 

### **Assumption 3**  
Given that item prices fluctuate between individual orders, items were aggregated by calculating the average price to facilitate analysis of pricing trends. It is important to note, however, that the total revenue calculation is based on the actual sum of revenue, not on the sum of the average unit prices. 

### **Assumption 4**  
There were 135,080 with blank spaces in CustomerID Column. These were not removed as they still represent genuine transactions and would still support goals listed above. Data was not grouped by transactions for any analysis as it felt pointless to do that while not having a significant chunk of 

### **Additional Assumptions and Caveats**  
For more information on the assumptions used and specific data-cleaning / data organization decisions made please see the following: 

# Works Cited  
1\. “Bestseller Lists and the Economics of Product Discovery.” Annual Review of Economics, Apr. 2017, pp. 89–93. [users.ssc.wisc.edu/\~atsorensen/papers/bestseller\_lists\_annreview.pdf](http://users.ssc.wisc.edu/~atsorensen/papers/bestseller_lists_annreview.pdf).

2\. Gue, Guen, guen and Universite de Bretagne-Sud, IUT de Vannes—Département TC, Laboratoire GRESICO. “Foot-in-the-door Technique and Computer-mediated Communication.” Computers in Human Behavior, vol. 18–18, 2002, pp. 11\. [www.communicationcache.com/uploads/1/0/8/8/10887248/foot-in-the-door\_technique\_and\_computer-mediated\_communication.pdf](http://www.communicationcache.com/uploads/1/0/8/8/10887248/foot-in-the-door_technique_and_computer-mediated_communication.pdf).  
