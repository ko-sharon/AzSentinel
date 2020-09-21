---
title: Sizing Guide
sidebar: mydoc_sidebar
permalink: guides_sizingguide.html
folder: guides
keywords: sizing
tags: [sizing]
---

## Average Daily MB: Billable vs Non-Billable

This query will calculate the Total Daily Volume (MB) of Billable and Non-Billable data sources ingested, over a 30-day Average.

```
// To calculate average daily log size (MB)
union withsource = source * 
| where TimeGenerated >= startofday(ago(30d)) and TimeGenerated < startofday(now())
| summarize
BillableMB = (sumif(_BilledSize, _IsBillable == "True")/1024/1024), 
NotBillableMB = (sumif(_BilledSize, _IsBillable == "False")/1024/1024)
by Day = bin(startofday(TimeGenerated), 1d)
| summarize MonthlyBillableMB = sum(BillableMB), MonthlyNotBillableMB = sum(NotBillableMB) //Total size of Billable and Non-Billable sources over 30 days
| project AvgDailyBillableMB = round(MonthlyBillableMB/30,0), AvgDailyNotBillableMB = round(MonthlyNotBillableMB/30,0) //Avg Daily Log Size of Billable and Non-Billable sources
```

## Average Daily MB: Per Data Source

This query will calculate the Daily Volume (MB) of Billable and Non-Billable data ingested, per Data Source, over a 30-day Average.

```
// To view logs by day (MB)
union withsource = source * 
| where TimeGenerated >= startofday(ago(30d)) and TimeGenerated < startofday(now())
| summarize
BillableMB = round(sumif(_BilledSize, _IsBillable == "True")/1024/1024, 0), 
NotBillableMB = round(sumif(_BilledSize, _IsBillable == "False")/1024/1024, 0)
by Day = bin(startofday(TimeGenerated), 1d)
```

## Absolute Daily MB: Billable vs Non-Billable

This query will calculate the Total Daily MB of Billable and Non-Billable data sources ingested, over the past 30 days.

```
// To view logs by day (MB)
union withsource = source * 
| where TimeGenerated >= startofday(ago(30d)) and TimeGenerated < startofday(now())
| summarize
BillableMB = round(sumif(_BilledSize, _IsBillable == "True")/1024/1024, 0), 
NotBillableMB = round(sumif(_BilledSize, _IsBillable == "False")/1024/1024, 0)
by Day = bin(startofday(TimeGenerated), 1d)
```

{% include links.html %}
