# Finbourne.Sdk.Lusid.Model.ShareClassRoundingConvention

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Precision** | **int** | Optional | The precision of the rounding: the number of decimal places, or of significant figures when PrecisionType is SignificantFigures. At most 28, and at least 1 for SignificantFigures. Defaults to 0. |
| **RoundingType** | **string** | Optional | The type of rounding, applied at the last decimal place or significant figure. Defaults to None, which leaves the value unrounded. Available values: None, Down, Up, Nearest. |
| **PrecisionType** | **string** | Optional | What Precision counts: DecimalPlaces (the default) or SignificantFigures. A SignificantFigures convention is not copied onto an instrument created for the share class. Available values: DecimalPlaces, SignificantFigures. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ShareClassRoundingConvention(
    precision: 0,  // optional — The precision of the rounding: the number of decimal places, or of significant figures when PrecisionType is SignificantFigures. At most 28, and at least 1 for SignificantFigures. Defaults to 0.
    roundingType: "...",  // optional — The type of rounding, applied at the last decimal place or significant figure. Defaults to None, which leaves the value unrounded. Available values: None, Down, Up, Nearest.
    precisionType: "..."  // optional — What Precision counts: DecimalPlaces (the default) or SignificantFigures. A SignificantFigures convention is not copied onto an instrument created for the share class. Available values: DecimalPlaces, SignificantFigures.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ShareClassRoundingConvention>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

