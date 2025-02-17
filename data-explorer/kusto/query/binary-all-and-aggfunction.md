---
title: binary_all_and() (aggregation function) - Azure Data Explorer
description: This article describes binary_all_and() (aggregation function) in Azure Data Explorer.
ms.reviewer: alexans
ms.topic: reference
ms.date: 09/05/2022
---
# binary_all_and() (aggregation function)

Accumulates values using the binary `AND` operation for each summarization group, or in total if a group is not specified.

[!INCLUDE [data-explorer-agg-function-summarize-note](../../includes/data-explorer-agg-function-summarize-note.md)]

## Syntax

`binary_all_and` `(`*Expr*`)`

## Arguments

| Name | Type | Required | Description |
|--|--|--|--|
| *Expr* | long | &check; | A long number used for the binary `AND`  calculation. |

## Returns

Returns an aggregated value using the binary `AND` operation over records for each summarization group, or in total if a group is not specified.

## Example

The following example produces `CAFEF00D` using binary `AND` operations:

**\[**[**Click to run query**](https://dataexplorer.azure.com/clusters/help/databases/Samples?query=H4sIAAAAAAAAA0tJLAHCpJxUjbzSXKuc/Lx0Ta5oLgUFgwo3KNBRQHANDNx0wDxniJwLhOfm6OYKVsoVy1WjUFyam5tYlFmVqlCUWlyaU6Jgq1CSX1pQkFqkUZKfkVqhkZSZl1hUGZ+YkxOfmJcCslhTUxMAwZHTS4kAAAA=)**\]**

```kusto
datatable(num:long)
[
  0xFFFFFFFF, 
  0xFFFFF00F,
  0xCFFFFFFD,
  0xFAFEFFFF,
]
| summarize result = toupper(tohex(binary_all_and(num)))
```

**Results**

|result|
|---|
|CAFEF00D|
