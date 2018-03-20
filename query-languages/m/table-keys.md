---
title: "Table.Keys | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2018"
ms.prod: "powerbi"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "mlang"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
ms.assetid: 337e589b-4ff2-49d1-bcf6-68a3c4f95413
caps.latest.revision: 7
author: "Minewiskan"
ms.author: "owend"
manager: "kfile"
---
# Table.Keys

  
## About  
Returns a list of key column names from a table.  
  
```  
Table.Keys(table as table) as list  
```  
  
## Arguments  
  
|Argument|Description|  
|------------|---------------|  
|table|Table to return a list of key column names from.|  
  
## Example  
  
```  
let  
  
    table = Table.FromRecords(  
  
    {  
  
        [CustomerID = 1, Name = "Bob", Phone = "123-4567"],  
  
        [CustomerID = 2, Name = "Jim", Phone = "987-6543"]  
  
}),  
  
    resultTable = Table.AddKey(table, {"CustomerID"}, true),  
  
    keys = Table.Keys(resultTable),  
  
    #"Table from List" = Table.FromList(keys, Splitter.SplitByNothing(), null, null, ExtraValues.Error),  
  
    #"Expand Column1" = Table.ExpandRecordColumn(#"Table from List", "Column1", {"Columns", "Primary"}, {"Column1.Columns", "Column1.Primary"}),  
  
    #"Expand Column1.Columns" = Table.ExpandListColumn(#"Expand Column1", "Column1.Columns")  
  
in  
  
    #"Expand Column1.Columns"  
```  
  
|Column1.Columns|Column1.Primary|  
|-------------------|-------------------|  
|CustomerID|1|  
  