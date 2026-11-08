# Finbourne.Sdk.Luminesce.Model.ExportNumberFormat

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MinDecimals** | **int?** | Optional | *No description available.* |
| **MaxDecimals** | **int?** | Optional | *No description available.* |
| **ThousandSeparator** | **bool** | Optional | *No description available.* |
| **DisplayAsPercentage** | **bool** | Optional | *No description available.* |
| **NegativeNumberFormat** | **ExportNegativeNumberFormat** | Optional | *No description available.* |
| **ExcelFormat** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ExportNumberFormat(
    minDecimals: 0,  // optional
    maxDecimals: 0,  // optional
    thousandSeparator: true,  // optional
    displayAsPercentage: true,  // optional
    negativeNumberFormat: ,  // optional
    excelFormat: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExportNumberFormat>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

