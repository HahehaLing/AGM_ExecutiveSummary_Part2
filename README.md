# AGM_ExecutiveSummary_Part2
Recommendations about Peak meal delivery via analyzing single-day Peak sales &amp; cross-referencing AGM sales. 

## Background provided by Kevin Crook
A few years ago, a new startup was born: Acme Gourmet Meals (AGM). AGM has just finished a very successful year on the enhanced computer systems, and now has a database of sales data for one year.

AGM executives are considering adding a delivery option, with the hopes of increasing sales, growing the customer base, and increasing profitability.

Management decided to do a proof of concept (POC) in the form of a three month trial run using one delivery service at the Berkeley store.

Management chose Peak Deliveries primarily because it's a newer operation with a model that takes a percentage cut of the product pricing instead of charging customers a delivery fee. Peak's cut is 18 %. So, for each $ 12 meal, approximately $2.16. Customers may tip the delivery driver if they wish. AGM is not given any visibility into customer tips. (Peak is protecting its data on good tippers.) Peak has an outstanding reputation for great, fast, and efficient deliveries, with excellent customer service. Peak will only deliver to zip codes within a 5 mile radius of the store.

### Product difference between Peak's system and AGM's system
For products, AGM will enter products into Peak's system. Peak will assign an ID in their system to the product. We will need to create a mapping table to map Peak's IDs to AGM's IDs. In AGM's case all products cost $12 and are tax exempt. AGM will mark them as exempt from sales tax.

### Customer identification difference between Peak's system and AGM's system
Regarding the customer list, AGM does not want to give out their full customer list to third parties. Customers will have to sign up with Peak, either using the website, the app, or by telephone. Our executives anticipate and understand that the trade off to not giving them our customer list is that we will probably have to validate and/or cleanse the customer data. Peak will assign their customer ID to each customer.

### Objective
AGM is currently considering meal-delivery options and the executives have asked me to analyze the preliminary Peak's sales data to provide recommendations on improving the business. 


## Data
The entity relations diagram (ERD) provided by Kevin Crook shows the relationship. 
![alt text](https://github.com/HahehaLing/AGM_ExecutiveSummary/blob/main/Sales%20Database%20ERD.jpeg)

The product [mapping between Peak and AGM's identifier](https://github.com/HahehaLing/AGM_ExecutiveSummary_Part2/blob/main/peak_product_mapping_to_agm.csv) is shown in.

## Outline
  - [Customer-specific Analysis](https://github.com/HahehaLing/AGM_ExecutiveSummary_Part2/blob/main/Customer_data_clean.ipynb)
    - cleaning and cross-examining the Peak's customers to AGM's using Soundex and FuzzyLogic
  - [Best Recommendation](https://github.com/HahehaLing/AGM_ExecutiveSummary_Part2/blob/main/Best_Recommendation.ipynb)
    - Meals sold from online delivery (Peak) vs. in-store purchases (AGM)
    - Distance impact on sales
    - Benefits of staging: quick analysis & recommendation on Peak's data collection process
    - Benefits of withholding customer list from Peak 

## Executive Summary
![alt text](https://github.com/HahehaLing/AGM_ExecutiveSummary_Part2/blob/main/distance_vs_spending.png)
![alt text](https://github.com/HahehaLing/AGM_ExecutiveSummary_Part2/blob/main/PeakvsAGM_valuedcustomer_boxplot.png)


### Meals sold

The same types of meals are popular for Peak's online ordering as AGM's own in-store sales with Pistachio Salmon continuing to sell the most and Chicken Salad selling the least. This means that we can't use the online ordering to capture customers that can get rid of the less-popular meals inventory(chicken salads, spinach orzo...etc.).

### Distance and Peak's online ordering
There does not seem to be a strong indication of distance from store and more online purchases with Peak's.  


### Benefit of Staging: Recommendation to Peak's data collection process
From the preliminary analysis with last notebooks' staging tables, AGM can reflect to Peak about some of the data collection suggestions / improvement we would like Peak to implement. Had we implemented a waterfall approach, we would not have been able to make the following suggestions (too late for Peak to make any adoptions to their data collections) to Peak:

1) include a section for preferred name (e.g. I for Israel)

2) remind customers to sign up in CORRECT and CONSISTENT (appostrophes, address without abbreviations) spelling as the ones used for AGM's sign up

3) have a section to ask if the customer is a first time customer. If the customer is a first comer, and not in AGM's database, there would obviously be a mismatch to AGM's records. This would also offer insights to whether our business is growing from the online ordering to new customer base. 


### Benefit of the current status-quo: Withhold customers list from Peak and Peak's delivery customers

Preliminary analysis done on October 3, 2020's Peak's sales shows that Peak does not deliver to the top 50 most-frequent and the top 50 highest spending in-store AGM customers. This may further strengthen my recommendation in [Notebook](https://github.com/HahehaLing/AGM_ExecutiveSummary_Part2/blob/main/Customer_data_clean.ipynb) of with-holding our customers information. If these high-value customers are not current Peak's customers and they continue to make the same in-store purchasing patterns, we would be netting a higher profit without cutting 18% commission to Peak. At present, only 40% of our top 50 highest value customers are within the 5 mi radius delivered by Peak, upon learning about the address information for the highest-value customers, Peak may extend their delivery range to 10 mi (average radius from store for 50 most-valuable customers are within 8.3 mi radius) and cut into our profit. 

At present, the customers Peak is delivering to are middle to lower valued customers in terms of money-spent and number of in-store visits. This customer group would be perfect for using Peak's services and expand growth for AGM as these customers simply don't come to the stores as often or spend as much as our most-valued in-store customers. At the expense of 18% of commission we give to Peak, we are hopefully offering convenience to these middle tier value customers. With time and further data provided as the trials proceed, by word of mouth and maybe more sales from the added convenience of online deliveries, these "middle" tier value customers may shift towards higher tiered customers.

# Authors
Eric (Yue) Ling

# Acknowledgments
Kevin Crook for guidance and data preparation and cleaning. https://github.com/kevin-crook-ucb
