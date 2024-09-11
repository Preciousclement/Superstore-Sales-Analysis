# Superstore Sales Analysis
This project involves analyzing sales data from a fictional superstore to uncover key business insights. 

## Table of Content
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools Used](#tools-used)
- [Objectives](#objectives)
- [Steps Taken](#steps-taken)
- [Key Insights](#key-insights)
- [Conclusion](#conclusion)

  
### Project Overview
The analysis of this project includes exploring sales patterns, previous year perfomance from current year, product performance, profits and regional trends . 
Using Excel and Tableau, the project aims to provide actionable recommendations for optimizing inventory, improving sales strategies, and enhancing customer satisfaction.

### Data Source 
The primary data set used for this analysis is from kaggle.com
The dataset consists of 9,995 rows with the folllowing attributes; Row ID, Order ID,	Order Date,	Ship Date,	Ship Mode,	Customer ID,	Customer Name,	Segment,	Country,	City,	State,	Postal Code,	Region,	Product ID,	Category,	Sub-Category,	Product Name,	Sales	Quantity,	Discount and	Profit	 	 

### Tools Used
- Excel
- Tableau 

### Objectives
1. Data Cleaning: Ensure data integrity by addressing inconsistencies, such as date formatting issues and missing values.
2. Exploratory Data Analysis (EDA): Identify trends and patterns within the data.
3. Visualization: Create visual representations of the insights to facilitate understanding and decision-making.

### Steps Taken
#### 1. Analyzed Requirements
- Understood the data
- The right requirements we collected, the right charts were choosen, as well as the colors
- Drew a mockup for guidance

#### 2. Building Data Source & Charts
- Data was cleaned with Excel
- Data was connected to Tableau and data model created
- Renamed fields and tables
- Crosschecked data types

- Created Calculated Fields:
        1. Current Year, Previous Year
        2. CY of Profit, Sales, Quantity, Orders and Customers
        3. PY of Profit, Sales, Quantity, Orders and Customers
        4. Min/Max of Profit, Sales, Quantity, orders and Customers
        5. % Difference of Profit, Sales, Quantity, orders and Customers
- Inputed a "select year" parameter
- Build charts accordingly
- Formatted the charts by cleaning up axis & headers. coloring and tooltip

```CALCULATED FIELDS CREATED

-- CY of Sales --
IF YEAR([Order Date]) = [Select Year] THEN [Sales]
END

-- CY Customer --
IF YEAR([Order Date]) = [Select Year] THEN [Customer ID] 
END
**Formular was also used for CY profit, quantity and orders**



-- PY of Sales --
IF YEAR([Order Date]) = [Select Year] - 1 THEN [Sales]
END

-- PY Customers --
IF YEAR([Order Date]) = [Select Year] - 1 THEN [Customer ID] 
END
**Formular was also used for PY profit, quantity and orders**



-- % Difference of Sales between years --
(SUM([CY Sales]) - SUM([PY Sales])) / SUM([PY Sales])

-- % Difference of Customers between years --
(COUNTD([CY Customers]) - COUNTD([PY Customers])) / COUNTD([PY Customers])
**Formular was also used for % Diff of profit, quantity and orders**



-- Min/Max of Sales --
IF SUM([CY Sales])= WINDOW_MAX(SUM([CY Sales]))
THEN SUM([CY Sales])
ELSEIF SUM([CY Sales])= WINDOW_MIN(SUM([CY Sales]))
THEN SUM([CY Sales])
END

-- Min/Mx of Customers --
IF COUNTD([CY Customers]) = WINDOW_MAX(COUNTD([CY Customers]))
THEN COUNTD([CY Customers])
ELSEIF COUNTD([CY Customers]) = WINDOW_MIN(COUNTD([CY Customers]))
THEN COUNTD([CY Customers])
END
**Formular was also used for Min/Max of profit, quantity and orders**

```
#### 3. Dashboard Setup
- Drew Mockups for containers
- Built the container stgructures
- Pull all the charts together
- Formatted the charts by distributing evenly, including legends and adding inner & outer paddings
- Included Icons, Filter and Dynamics
  
**Dashbord**

Published on Tableau Public: 

Screenshots:
<

### Key Insights
1. 


