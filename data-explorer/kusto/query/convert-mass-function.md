---
title: convert_mass() - Azure Data Explorer
description: This article describes convert_mass() in Azure Data Explorer.
ms.reviewer: itsagui
ms.topic: reference
ms.date: 07/03/2022
---
# convert_mass

Convert a mass value from one unit to another.

## Syntax

`convert_mass(`*value*`,`*from*`,`*to*`)`

## Arguments

| Name | Type | Required | Description |
|--|--|--|--|
| `value` | real | &check; | The value to be converted. |
| `from` | string | &check; | The unit to convert from. For possible values, see [Conversion units](#conversion-units). |
| `to` | string | &check; | The unit to convert to. For possible values, see [Conversion units](#conversion-units). |

### Conversion units

* Centigram
* Decagram
* Decigram
* EarthMass
* Grain
* Gram
* Hectogram
* Kilogram
* Kilopound
* Kilotonne
* LongHundredweight
* LongTon
* Megapound
* Megatonne
* Microgram
* Milligram
* Nanogram
* Ounce
* Pound
* ShortHundredweight
* ShortTon
* Slug
* SolarMass
* Stone
* Tonne

## Returns

 Returns the input value converted from one mass unit to another.

## Examples

**\[**[**Click to run query**](https://dataexplorer.azure.com/clusters/help/databases/Samples?query=H4sIAAAAAAAAAysoyswrUShKLS7NKVGwVUjOzytLLSqJz00sLtYw1DPSUVD3zszJTy9KzFUHsgPyS/NS1DUBemVMijUAAAA=)**\]**

```kusto
print result = convert_mass(1.2, 'Kilogram', 'Pound')
```

|result|
|---|
|2.64554714621853|
