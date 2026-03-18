# Finbourne.Sdk.Lusid.Model.FxForwardModelOptions

> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ForwardRateObservableType** | **string** | Required | The available values are: ForwardPoints, ForwardRate, RatesCurve, FxForwardCurve, Invalid |
| **DiscountingMethod** | **string** | Required | The available values are: Standard, ConstantTimeValueOfMoney, Invalid |
| **ConvertToReportCcy** | **bool** | Required | Convert all FX flows to the report currency  By setting this all FX forwards will be priced using Forward Curves that have Report Currency as the base. |
| **ModelOptionsType** | **string** | Required | The available values are: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions Default: `ModelOptionsTypeEnum.FxForwardModelOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxForwardModelOptions(
    forwardRateObservableType: "...",  // required — The available values are: ForwardPoints, ForwardRate, RatesCurve, FxForwardCurve, Invalid
    discountingMethod: "...",  // required — The available values are: Standard, ConstantTimeValueOfMoney, Invalid
    convertToReportCcy: true,  // required — Convert all FX flows to the report currency  By setting this all FX forwards will be priced using Forward Curves that have Report Currency as the base.
    modelOptionsType: "..."  // required — The available values are: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FxForwardModelOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

