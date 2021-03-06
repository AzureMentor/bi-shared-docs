---
title: "Analysis Services tabular model programming for compatibility level 1200 | Microsoft Docs"
ms.date: 10/23/2019
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Tabular model programming for compatibility level 1200 and higher

[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]

Beginning with compatibility level 1200, tabular metadata is used to describe model constructs, replacing historical multidimensional metadata as descriptors for tabular model objects. Metadata for tables, columns, and relationships are table, column, and relationship, rather than the multidimensional equivalents (dimension and attribute).  
  
You can create new models at compatibility level 1200 or higher by using the Microsoft.AnalysisServices.Tabular APIs, the latest version of Visual Studio with Analysis Services projects, or by changing the **CompatibilityLevel** of an existing tabular model to upgrade it (also done in Visual Studio). Doing so binds the model to newer versions of the server, tools, and programming interfaces.   
  
Upgrading an existing tabular solution is recommended but not required. Existing script and custom solutions that access or manage tabular models or databases can be used as-is. Azure Analysis Services supports compatibility level 1200 and higher only.
  
 New Tabular models will require different code and script, summarized below.  
  
## Object model definitions as tabular metadata constructs

 The Tabular Object Model for 1200 or higher models is exposed in JSON through the [Tabular Model Scripting Language](https://docs.microsoft.com/bi-reference/tmsl/tabular-model-scripting-language-tmsl-reference) and through the AMO data definition language through a new namespace, [Microsoft.AnalysisServices.Tabular](https://msdn.microsoft.com/library/microsoft.analysisservices.tabular.aspx)

## Script for tabular models and databases

 TMSL is a JSON scripting language for Tabular models, with support for create, read, update, an delete operations. You can refresh data via TMSL and invoke database operations for attach, detatch, backup, restore, and synchronize.  
  
 AMO PowerShell accepts TMSL script as input.  
  
 See [Tabular Model Scripting Language &#40;TMSL&#41; Reference](https://docs.microsoft.com/bi-reference/tmsl/tabular-model-scripting-language-tmsl-reference) and [Analysis Services PowerShell Reference](../../analysis-services/powershell/analysis-services-powershell-reference.md) for more information.  
  
## Query languages

 DAX and MDX are supported for all tabular models.  
  
## Expression language

 Filters and expressions used to create calculated objects, including measures and KPIs, are formulated in DAX. See [Understanding DAX in Tabular Models](../../analysis-services/tabular-models/understanding-dax-in-tabular-models-ssas-tabular.md) and [Data Analysis Expressions &#40;DAX&#41; in Analysis Services](https://msdn.microsoft.com/library/abb336c9-3346-4cab-b91b-90f93f4575e5).  
  
## Managed code for tabular models and databases

 AMO includes a new namespace, Microsoft.AnalysisServices.Tabular, for working with models programmatically. See [Microsoft.AnalysisServices Namespace](https://msdn.microsoft.com/library/ms146720\(SQL.130\).aspx) for more information.  
  
> [!NOTE]  
>  Analysis Services Management Objects (AMO), ADOMD.NET, and Tabular Object Model (TOM) client libraries now target the .NET 4.0 runtime.   
  
## See also

 [Analysis Services Developer Documentation](../../analysis-services/analysis-services-developer-documentation.md)   
 [Tabular Model Programming for Compatibility Levels 1050 through 1103](../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/tabular-model-programming-for-compatibility-levels-1050-through-1103.md)   
 [Technical Reference](../../analysis-services/powershell/analysis-services-powershell-reference.md)     
 [Compatibility levels of Tabular models and databases](../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/tabular-model-programming-for-compatibility-levels-1050-through-1103.md)   
  
  
