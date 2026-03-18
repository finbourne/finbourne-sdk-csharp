# Finbourne.Sdk.Lusid.Model.EquityModelOptions

Model options for equity related pricing.
> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EquityForwardProjectionType** | **string** | Required | Determines how forward equity prices should be projected.                Supported string (enumeration) values are: [FlatForwardCurveFromSpot, EquityCurveByPrices, ForwardProjectedFromRatesCurve]. |
| **ModelOptionsType** | **string** | Required | The available values are: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions Default: `ModelOptionsTypeEnum.EquityModelOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EquityModelOptions(
    equityForwardProjectionType: "...",  // required — Determines how forward equity prices should be projected.                Supported string (enumeration) values are: [FlatForwardCurveFromSpot, EquityCurveByPrices, ForwardProjectedFromRatesCurve].
    modelOptionsType: "..."  // required — The available values are: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EquityModelOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

