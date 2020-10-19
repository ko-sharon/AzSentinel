---
title: Sizing Guide
sidebar: mydoc_sidebar
permalink: guides_sizingguide.html
folder: guides
keywords: sizing
tags: [sizing]
---

## Pre-Ingestion into Sentinel

Sizing is (and always has been) a tricky issue with SIEMs, even if you do have an existing tool, the unit of measure may be based on different metrics (example GB/day vs Events per Second, EPS) for different vendors. 

### I have an Existing SIEM/LMS
* If your existing SIEM/LMS is already measured based on data volume ingested (GB/day), then that would be the same as Azure Sentinel.
* Else if your existing solution is measured based on other metrics (EPS etc.), you can typically pivot into the log / data storage portal to look for how much data has been stored over the past perhaps 30 days and divide the absolute amount by 30 to get the average GB/day. 
* The above would be more accurate than assuming a generic average packet size per event and multiplying that by EPS observed (given that packet sizes can vary a lot depending on the data source).

### I do not have an Existing SIEM/LMS
* Ideally, logging your data over a period of time would provide the most accurate gauge on how much data is generated. The KQL queries in the next section can then be used to determine specifically how much data is generated per data source (and whether it is billable or not).
* Otherwise, there are many publicly available calculators (for example <a alt='calculator' href='https://siemsizingcalculator.logpoint.com/'>this link</a>) that provide data volume approximations (GB/day) based on estimated packet size and a corresponding EPS per data source. This is useful in providing a rough order of magnitude.

## Post-Ingestion into Azure Sentinel

While the total ingestion of data into Azure Sentinel can be seen by navigating to your Azure Sentinel `Settings` blade, a common request is to view a more granular breakdown by data source or day and the amount of billable and non-billable data ingested. The following KQL queries can be run in the `Logs` blade to extract these values.  

### Average Daily MB: Billable vs Non-Billable

This query will calculate the Total Daily Volume (MB) of Billable and Non-Billable data sources ingested, over a 30-day Average.

```
// To calculate average daily log size (GB)
union withsource = source * 
| where TimeGenerated >= startofday(ago(30d)) and TimeGenerated < startofday(now())
| summarize
BillableGB = (sumif(_BilledSize, _IsBillable == "True")/1024/1024/1024), 
NotBillableGB = (sumif(_BilledSize, _IsBillable == "False")/1024/1024/1024)
by Day = bin(startofday(TimeGenerated), 1d)
| summarize MonthlyBillableGB = sum(BillableGB), MonthlyNotBillableGB = sum(NotBillableGB) //Total size of Billable and Non-Billable sources over 30 days
| project AvgDailyBillableGB = round(MonthlyBillableGB/30,0), AvgDailyNotBillableGB = round(MonthlyNotBillableGB/30,0) //Avg Daily Log Size of Billable and Non-Billable sources
```
![alt text](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/Sizing_AvgDailyMBBillableNonBillable.png?raw=true)

### Average Daily MB: Per Data Source

This query will calculate the Daily Volume (MB) of Billable and Non-Billable data ingested, per Data Source, over a 30-day Average.

```
// To view average daily log size by source (GB)
union withsource = source * 
| where TimeGenerated >= startofday(ago(30d)) and TimeGenerated < startofday(now())
| summarize
AvgDailyBillableMB = round(sumif(_BilledSize, _IsBillable == "True")/1024/1024/1024, 0)/30, 
AvgDailyNotBillableMB = round(sumif(_BilledSize, _IsBillable == "False")/1024/1024/1024, 0)/30
by source
```
![alt text](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/Sizing_AvgDailyMBperDataSource.png?raw=true)

### Absolute Daily MB: Billable vs Non-Billable

This query will calculate the Total Daily MB of Billable and Non-Billable data sources ingested, over the past 30 days.

```
// To view logs by day (GB)
union withsource = source * 
| where TimeGenerated >= startofday(ago(30d)) and TimeGenerated < startofday(now())
| summarize
BillableMB = round(sumif(_BilledSize, _IsBillable == "True")/1024/1024/1024, 0), 
NotBillableMB = round(sumif(_BilledSize, _IsBillable == "False")/1024/1024/1024, 0)
by Day = bin(startofday(TimeGenerated), 1d)
```
![alt text](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/Sizing_AbsDailyMBBillableNonBillable.png?raw=true)

{% include links.html %}
