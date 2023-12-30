# **Dimensional Data Model (Star Schema) **
# 1. What is dimensional data model?
Is a denormalization technique, where a fact table is surrounded by multiple dimensions and constraint by primary and foreign keys
# 2. Importance of Dimensional Data model
- To ensure data quality and accuracy in a database
- To define relationships, primary and foreign keys
- To provide optimized database for fast queries  
# 3. Difference Between Dimension, Fact, Fact Tables
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
# 5. Examples 
In real life, as a Data Analyst, we often build dimensional data model from existing database. 
Below is the simple data model generated by ChatGPT (and I add some more information)
![](images/Delivery Data Model.png)
