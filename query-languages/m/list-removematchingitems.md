---
title: "List.RemoveMatchingItems | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2018"
ms.prod: "powerbi"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "mlang"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
ms.assetid: 4285af33-6f6e-451b-84e3-768b7403678a
caps.latest.revision: 5
author: "Minewiskan"
ms.author: "owend"
manager: "kfile"
---
# List.RemoveMatchingItems

  
## About  
Removes all occurrences of the given values in the list.  
  
```  
List.RemoveMatchingItems(list as list, values as list, optional equationCriteria as any) as list  
```  
  
## Arguments  
  
|Argument|Description|  
|------------|---------------|  
|list|The List to modify.|  
|values|The list of values to remove.|  
|optional equationCriteria|An optional equation criteria value to control equality comparison. For more information about the equationCriteria, see Parameter Values.|  
  
## Example  
  
```  
List.RemoveMatchingItems ({"A", "B", "C", "B", "A"}, {"A", "C"}) equals {"B", "B"}  
```  