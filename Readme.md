# Readme

### Background

Northwind is a fictional company that sells specialty food products in bulk (wholesale). They have moderate amounts of data from 2013 to 2015 that provides details regarding the orders, products, product categories as well as their customers.

This project thoroughly analyzes the available data and provides insights for the company’s success. The following recommendations are provided:

- **Sales Trend Analysis** - examination of sales data over numerous time periods to identify patterns, seasonal fluctuations, or emerging trends that can help inform business decisions.
- **Product Level Performance** - evaluation of individual products’ sales, profitability, and overall market performance to determine which items are driving business growth, and which may require adjustments or further discontinuation.
- **Customer Retention Analysis -** customer behavior and loyalty patterns to understand the factors that influence repeat purchases, improve customer satisfaction, and reduce churn rates, ensuring long-term business growth.

---

### Data Structure

The main database structure as seen below consists of customers, employees, orders, shippers, categories, order_details and products. A description of each table as is follows:

![Untitled Diagram.drawio.png](Readme%201f8f00a5193d42bda92aaf0e21e0774f/Untitled_Diagram.drawio.png)

- **customers** - contains details for all the customers. *string_field_0* corresponds to the customer ID of the orders table.
- **orders** - contains transactional (including logistics) details for the executed orders.
- **categories** - contains categorical details of a specific product.
- **order_details** - contains itemized details for a specific order.
- **products** - contains product details of all the products sold by Northwind.
    
    *These are the SQL [](https://gist.github.com/korbsanity/eda78afdc3f725a3340558cff2782095)queries ([link](https://gist.github.com/korbsanity/eda78afdc3f725a3340558cff2782095)) used to check data integrity (cleanliness) - data is clean, no irregularities found*
    

---

### Summary

The company has shown an upward trend in sales hitting a significant mark on sales on April 2015 with $134,621. All months of 2015 so far also marked the highest months in sales with an average M-o-M of +10.43%. This can be attributed to the very diverse markets on Europe and Americas that has varying taste in different product categories. 

An interactive tableau sales dashboard of some key metrics are shown below and can be manipulated on [this link](https://public.tableau.com/views/NorthwindTraders_17265654955170/main_db?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link). 

![main_db.png](Readme%201f8f00a5193d42bda92aaf0e21e0774f/main_db.png)

---

### Deep Insights

**Sale Trends**

- **April 2015**: This month recorded the highest sales, with a total of **$134,621**.
- **Overall Trend**: There was a steady increase in sales over time, with the highest average daily sales occurring in **February 2015**.
- **Peak Sales**: Sales peaked during the first quarter (Q1) of 2015, reaching a total of **$315,219**.
- **Total Sales**: From **July 2013 to May 2015**, the total sales amounted to **$1,354,458.59**.

**Product Performance**

- **Overall Sales:** Beverages had the highest overall sales, followed closely by Confectionaries.
    - For 2013 and 2015 (which have incomplete data), beverage products led in sales, with dairy coming in second. In 2014 (complete data), beverages ranked second.
    - **Beverages:**
        - **Côte de Blaye**: This product was consistently the top-selling beverage, accounting for 52% of total beverage sales.
            - There was a steady increase in sales, with a notable upward trend beginning in February 2015.
            - High sales in this period can be attributed to the Valentine’s, Saint Patrick’s Day and Easter celebrations which are common holidays.
    - **Dairy Products:**
        - **Raclette Courdavault** and **Camembert Pierrot**: These two products accounted for 50% of all dairy sales.
            - **Raclette Courdavault** experienced a significant surge in popularity in April 2015, generating $17,170 in sales (compared to its 2014 monthly average of $3,159), which contributed to an overall rise in dairy sales during that period.
- **Low Performers:**
    - **Grains and Cereals:** This category had the lowest overall sales, followed by **Produce**.
        - **Filo Mix**: Among grains and cereals, Filo Mix had the lowest gross sales, generating only $3,383 for the entire dataset, which represents 0.25% of total sales.
        - **Tofu and Longlife Tofu**: In the produce category, these products recorded the lowest sales, with a combined total of $11,194, representing 0.8% of total sales.
        - The following products meanwhile, belong to the [bottom 20%](https://gist.github.com/korbsanity/457dead6ae8d8fa4ab8b5b89553b7214) of total product sales and should be considered for discontinuation.
            
            ![image.png](Readme%201f8f00a5193d42bda92aaf0e21e0774f/image.png)
            
- **Discontinued Products:** Upon analyzing discontinued products, it was [**found**](https://gist.github.com/korbsanity/b3c0251b3e5d3e47619d6ad4f5e73e56) that **Thüringer Rostbratwurst** and **Alice Mutton** had made significant contributions to total sales before being discontinued, with sales of $87,736.40 (6.47% of total) and $35,482.20 (2.62% of total) respectively.
    - **Thüringer Rostbratwurst** is also the product with the second-most total sales overall.

![image.png](Readme%201f8f00a5193d42bda92aaf0e21e0774f/image%201.png)

**Customers**

- Biggest Customers - Ernst Handel, QUICK-Stop and Save-a-lot Markets are the biggest customers. Together they almost make 25% of total sales out of 92 companies/customers listed on the dataset.
    - Overall the sales for these companies have been volatile, nut projects an upward trend. This suggests that these three rely heavily on few product categories/products. Expanding into new product lines or complementary products can help reduce reliance in one product.
    - **Ernst Handel**: $113,229 (8%)
        - Focuses mainly on Dairy and Condiments, spending $26,628 on Dairy  and $15,583 on condiment products.
    - **Save-a-lot Markets**: $115,664 (8%)
        - Focuses mainly on Meat and Dairy products, spending $30,793 on Meat and $23,773 on dairy products.
    - **QUICK-Stop**: $117,477 (8%)
        - Primarily buys Beverages and Confections, with $38,271 spent on Beverages and $18,634 on Confections.
        - Had a record high sales of beverages in February 2015 ($17,250)

![image.png](Readme%201f8f00a5193d42bda92aaf0e21e0774f/image%202.png)

- **Customer Lifetime Value (CLV)** - CLV was also [computed](https://gist.github.com/korbsanity/396b9dce94a1620673927ea9ede57cf6) which is the metric which estimates the lifetime value of a customer based on their total sales and order frequency. The following tops out of 92 companies/customers listed in the dataset.
    - Targeted promotions, discounts or loyalty perks can be offered to the companies with the highest CLVs. The utmost customer support should also be maintained for these customer's satisfaction.
    
    ![image.png](Readme%201f8f00a5193d42bda92aaf0e21e0774f/image%203.png)
    

**Geographical Sales Analysis**

**Beverages dominate in the Americas**:

- **Venezuela**: stands out as the only country where Dairy products top the sales.
- **USA**: Leads in overall sales and is the top global consumer of beverages.
    - Boise in Idaho has significant amount of sales in Meat & Poultry

![image.png](Readme%201f8f00a5193d42bda92aaf0e21e0774f/image%204.png)

**Europe shows similar trends with some outliers**:

- **Ireland & Spain**: Higher sales of Dairy and Meat & Poultry than beverages.
- **Portugal**: Condiments are the top-seller, surpassing beverages.
- **France**: Categories are almost equal in sales with Seafood, having the slight edge.
- **Austria & Finland**: Dairy products lead the sales.
- **Germany**: Dominates beverage sales, ranking second worldwide, and is the top consumer of Dairy.
    - In February 2015, $17,295 worth of beverages were sold, marking the highest sales month.

![image.png](Readme%201f8f00a5193d42bda92aaf0e21e0774f/image%205.png)

---

### Caveats and Assumptions

- Certain data from 2013 to 2015 are missing from the dataset. Since this data is fictional, no imputation was applied. Analysis done only accounts for available data.
- No sales table exists in the dataset. The sales data used for different metrics were computed from the *order_details* table where:

$$
Sales = [unitPrice]*[quantity]
$$
