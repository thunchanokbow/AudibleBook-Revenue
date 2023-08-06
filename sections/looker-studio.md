This will show how to building dashboard with [Looker Studio](https://lookerstudio.google.com/navigation/reporting)


Data Visualization
============

#### Check that this step has been completed before START 

1. Create table in BigQuery
2. Creating view, filtering some data for dashboard
<br>
   
[Create view in BigQuery](looker-studio.md#Create-view-in-BigQuery)

[Connect Looker Studio with data sources](looker-studio.md#connect-looker-studio-with-data-sources)

[Wireframe Requirement](looker-studio.md#Wireframe-Requirement)
-  [Dashboard Overview](looker-studio.md#Dashboard-Overview)

   - [Total Revenue Thailand](looker-studio.md#Total-Revenue-Thailand)
   - [Total Customers Thailand](looker-studio.md#Total-Customers-Thailand)
   - [Create Drop Down Filter](looker-studio.md#Create-Drop-Down-Filter)
   - [Revenue By Country](looker-studio.md#Revenue-By-Country)
   - [Transaction By Country](looker-studio.md#Transaction-By-Country)
   - [Best Selling Books](looker-studio.md#Best-Selling-Books )
   - [Best Selling Categories](looker-studio.md#Best-Selling-Categories )

- [Search Books By Revenue](looker-studio.md#Search-Books-By-Revenue)

## Create view in BigQuery 
A view is a virtual table defined by a SQL query that you can then authorize other users to access the data from the table.

![view](/images/create-view.png)


## Connect Looker Studio with data sources
![connect to bigquery](/images/connect.png)

## Wireframe Requirement
[Audible Books Dashboard](https://lookerstudio.google.com/s/pvyQ71p2cSg)
![overview](/images/overview.png)

## Dashboard Overview
### Total Revenue Thailand

- Add a chart to create column named “Total Revenue”.<br>
- Metrics : THBPrice.<br>
- Aggregation : SUM.<br>
- Type : Currency Thai Baht-THB.<br>

![totalrevenue](/images/totalrevenue.png)

### Total Customers Thailand

- Add a chart to create column named “Total Customers”.<br>
- Metrics : user_id.<br>
- Aggregation : Count Distinct. <br>
- Type : Number.<br>

### Create Drop Down Filter 
<br>
<p align="center">Drop Down Filter Country-Month Year</p>

![CountryMonth](/images/drop.png)

Country-Month Year<br>

- Add a control make a Drop-down list.<br>
- Rename : Country, Month Year.<br>
- Control field : country , timestamp.<br>
- Type : Number.<br>
- Metrics : user_id, Record Count.<br>
- Type of Month Year Column : Date and Time : Year Month.<br>

![dropdown](/images/dropdown.png)

### Revenue By Country 

- Insert text to create the title of “Revenue By Country”.<br>
- Add a chart to sync data from Google Maps.<br>
- Field Location : country.<br>
- Size : THBPrice.<br>

![googlemap](/images/googlemap.png)


### Transaction By Country 

- Add a chart to create “Bar Chart” of transaction of each country.<br>
- Dimension : country.<br>
- Metrics : Record Count.<br>

![Bar Chart](/images/barchart.png)

### Best Selling Books

- Add a chart to create “Table Chart” of the best selling books.<br>
- Dimension : Book_Title.<br>
- Metrics : THBPrice and rename to Revenue.<br>

![BestSelling Books](/images/bestsellingbook.png)

### Best Selling Categories

- Add a chart to create “Three Chart” of the best selling categories.<br>
- Dimension : Categories.<br>
- Metrics : THBPrice and rename to Revenue.<br>

![BestSelling Categories](/images/threechart.png)
<br>
<br>
<br>

## Search Books By Revenue

![Sold9](/images/9million.png)
<br>

<p align="center">Books that has generated more than 9 million baht in revenue</p>

- Add a parameter named Min_Revenue that uses Number(whole) and has a range of 0 to 30 million.<br>
- Add a control to allow users to access our parameter. Use a slider and control field: Min_Revenue.<br>


![Parameter](/images/parameter.png)
<br>
- Add a field to SQL to manage data in a parameter.<br>
- Add a table with dimension Book_id and metric Revenue.<br>
- Add a filter to the table named rev_filter. Set the filter to include More_than_min_rev and set Equal to (=) “1”. <br>

![More Than min rev](/images/last.png)
<p align="center">Books that has generated more than 24 million baht in revenue</p>

![Sold24](/images/24million.png)

