# Dimensional Data Model

# Table of content 
1.  What is dimensional data model?
   - Definition
   - Importance in Data Warehousing and Business Intelligence
2. Type of Dimensional Data Model
   - Star Schema
   - Snowflake Schema
   - Constellation Schema
3. Component of Star Schema 
   - Fact Table 
   - Dimension Table
   - Attributes and Hierarchies
4. Dimensional Data Model Design Process
5. Case Study 


# 1. What is dimensional data model?
- Definition
  
  A Dimensional Data Model is a structured framework for organizing and analyzing data efficiently, emphasizing simplicity for reporting and analysis
- Importance in Data Warehousing and Business Intelligence
  
  Crucial for constructing decision support systems in data warehousing and business intelligence, enabling organizations to extract meaningful insights from data.
# 2. Type of Dimensional Data Model
  - Star Schema
    + characterized by a central fact table connected to multiple dimension tables
    + the fact table contains quantitative data, and dimensions provide context with descriptive information
    + an efficient choice for many business intelligence applications because of the simplicity and ease of querying
      ![Star Schema](images/star_schema.png)
  - Snowflake Schema
    + an extension of the star schema where dimension tables are normalized
    + more complexity in queries and maintenance
      ![Snowflake Schema](images/snowflake_schema.png)
  - Constellation Schema
    + is not a standalone schema but a collection of multiple star schemas that share some common dimensions
    + each star schema corresponds to a specific business process, and shared dimensions enable integration and analysis across different processes
    + provides flexibility in handling diverse business requirements
      ![Constellation Schema](images/constellation_schema.jpg)
  - Comparison
    
      | Aspect | Star Schema | Snowflake Schema | Constellation Schema |
      | -------- | -------- | -------- | ---------| 
      | Structure | Centralized structure with a single fact table | Centralized structure, but dimensions are normalized | Collection of multiple star schemas sharing common dimensions|
      | Complexity | Simple structure with less complexity | More complex due to normalized dimensions | Varied complexity based on the structure of individual star schemas|
      |Dimensions|Denormalized dimensions for easy querying|Normalized dimensions, more storage efficiency|Shared and specific dimensions for different business processes|
      |Query Performance|Generally faster due to denormalized structure|May have slightly slower performance due to joins|Performance can vary based on the structure of individual star schemas|
      |Maintenance|Easier to maintain with fewer tables|More challenging maintenance due to normalization|Maintenance may involve updates across multiple star schemas|
      |Storage Space|May require more storage space|Can save storage space through normalization|Storage space can vary based on the structure of individual star schemas|
      |Flexibility|More rigid, but efficient for specific use cases|Offers flexibility with normalized dimensions|Flexible, accommodating diverse business requirements|

   - In practical terms, companies utilize a range of business processes, with the Constellation Schema being a frequently employed tool for business intelligence. Below, I provide details about the Constellation Schema, but for simplicity, I refer to it as the Star Schema (Constellation Schema based on Star Schema)
    
# 3. Components of Star Schema
   First, we need understand facts 
   - These are numerical values
   - Represents the performance measures of the business activity
   - Examples: Productivity, expenses, sales, profit, prices, quantity
   - Facts are also called measures. They are stored in the fact table

   A star schema has four main components: Fact table, Dimension tables, Attributes, Attribute hierarchies
   - Fact Table
     + Definition
       The fact table in each star schema holds quantitative data specific to the corresponding business process. It serves as the central repository for measurable metrics
     + Properties
     + Type of fact table
    
   - Dimension Table
     + Definition
     + Properties
     + Type of dimension table
       
   - Attributes and Hierarchies
# 4. Dimensional Data Model Design Process
- Identify the business process: The operational activities being modeled
- Declare the grain: The lowest level of information
- Define Dimension Tables: Contain the descriptive entities of the data
- Identify the Facts: are the numeric measurements that result from a business process

  A Fact Table contains:
  + The numeric measures
  + Foreign keys of the associated dimensions
  + Degenerate dimension keys
  + Date/time stamps
# 5. Case Study 
In the realm of data analysis, it's common for Data Analysts to construct dimensional data models based on existing databases. The following is a simple model generated by ChatGPT, with additional tables and attributes based on my experience

It's designed for a Delivery Company, managing aspects like order creation, pickup, dropoff, and payment

![Delivery](images/delivery_data_model.png)

Step 1: Identify the business process
- Process of order creation 
- Process of fulfillment
- Process of payment

Step 2: Declare the grain 
