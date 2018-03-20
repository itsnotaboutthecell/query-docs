---
title: "NEXTMONTH Function (DAX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/28/2017"
ms.prod: "powerbi"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "daxlang"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "sql13.as.daxref.NEXTMONTH.f1"
helpviewer_keywords: 
  - "NEXTMONTH function"
ms.assetid: 4a4e0a51-f692-464f-8c5a-07b39d9cf22d
caps.latest.revision: 8
author: "Minewiskan"
ms.author: "owend"
manager: "kfile"
---
# NEXTMONTH Function (DAX)
Returns a table that contains a column of all dates from the next month, based on the first date in the **dates** column in the current context.  
  
## Syntax  
  
```  
NEXTMONTH(<dates>)  
```  
  
#### Parameters  
  
|||  
|-|-|  
|Term|Definition|  
|**dates**|A column containing dates.|  
  
## Return Value  
A table containing a single column of date values.  
  
## Remarks  
This function returns all dates from the next day to the first date in the input parameter. For example, if the first date in the **dates** argument refers to June 10, 2009; then this function returns all dates for the month of July, 2009.  
  
The **dates** argument can be any of the following:  
  
-   A reference to a date/time column.  
  
-   A table expression that returns a single column of date/time values.  
  
-   A Boolean expression that defines a single-column table of date/time values.  
  
> [!NOTE]  
> Constraints on Boolean expressions are described in the topic, [CALCULATE Function &#40;DAX&#41;](calculate-function-dax.md).  
  
This DAX function is not supported for use in DirectQuery mode. For more information about limitations in DirectQuery models, see  [http://go.microsoft.com/fwlink/?LinkId=219172](http://go.microsoft.com/fwlink/?LinkId=219172).  
  
## Example  
The following sample formula creates a measure that calculates the 'next month sales' for the Internet sales.  
  
To see how this works, create a PivotTable and add the fields, CalendarYear and MonthNumberOfYear, to the **Row Labels** area of the PivotTable. Then add a measure, named **Next Month Sales**, using the formula defined in the code section, to the **Values** area of the PivotTable.  
  
```  
=CALCULATE(SUM(InternetSales_USD[SalesAmount_USD]), NEXTMONTH('DateTime'[DateKey]))  
```  
  
## See Also  
[Time Intelligence Functions &#40;DAX&#41;](time-intelligence-functions-dax.md)  
[Date and Time Functions &#40;DAX&#41;](date-and-time-functions-dax.md)  
[NEXTDAY Function &#40;DAX&#41;](nextday-function-dax.md)  
[NEXTQUARTER Function &#40;DAX&#41;](nextquarter-function-dax.md)  
[NEXTYEAR Function &#40;DAX&#41;](nextyear-function-dax.md)  
[Get Sample Data](http://go.microsoft.com/fwlink/?LinkId=164474)  
  