This will show how to building dashboard with [Looker Studio](https://lookerstudio.google.com/navigation/reporting)


Data Visualization
============
[Audible Books Dashboard](https://lookerstudio.google.com/s/pvyQ71p2cSg)

[Connect Looker Studio with data sources](section/looker-studio.md#Connect-Looker-Studio-with-data-sources)

[Dashboard Overview](section/looker-studio.md#Dashboard-Overview)

- [Total Revenue Thailand](section/looker-studio.md#Total-Revenue-Thailand)
- [Total Customers Thailand](section/looker-studio.md#Total-Customers-Thailand)
- [Create Drop Down Filter ( Country, Month Year) ](section/looker-studio.md#Create-Drop-Down-Filter ( Country, Month Year) )
- [Revenue By Country](section/looker-studio.md#Revenue-By-Country)
- [Transaction By Country](section/looker-studio.md#Transaction-By-Country )


## Check that this step has been completed before START 

1. Create table in BigQuery
2. Creating view, filtering some data for dashboard


## Connect Looker Studio with data sources

![connect to bigquery](/images/connect.png)

## Dashboard Overview
![overview](/images/overview.png)

### Total Revenue Thailand

- Add a chart to create column named “Total Revenue”<br>
- Metrics : THBPrice<br>
- Aggregation : SUM<br>
- Type : Currency Thai Baht-THB<br>

![totalrevenue](/images/totalrevenue.png)

### Total Customers Thailand

- Add a chart to create column named “Total Customers”<br>
- Metrics : user_id<br>
- Aggregation : Count Distinct <br>
- Type : Number<br>

### Create Drop Down Filter ( Country, Month Year) 
- Add a control make a Drop-down list<br>
- Rename : Country, Month Year<br>
- Control field : country , timestamp<br>
- Type : Number<br>
- Metrics : user_id, Record Count<br>
- Type of Month Year Column : Date and Time : Year Month<br>

![dropdown](/images/dropdown.png)

### Create Map : Revenue By Country 

- Insert text to create the title of “Revenue By Country”<br>
- Add a chart to sync data from Google Maps<br>
- Field Location : country<br>
- Size : THBPrice<br>

![googlemap](/images/googlemap.png)


### Create Bar Chart : Transaction By Country 

- Add a chart to create “Bar Chart” of transaction of each country<br>
- Dimension : country<br>
- Metrics : Record Count<br>

![Bar Chart](/images/barchart.png)









Dimension and Metric in chart
Workshop 6: Building dashboard with Google Data Studio (Data from BigQuery))

